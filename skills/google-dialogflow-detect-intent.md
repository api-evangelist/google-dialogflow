---
name: google-dialogflow-detect-intent
description: Send a conversation turn to a Dialogflow CX or ES agent and read back the agent's response, correctly handling session lifetime, language, billing and the fact that a retried turn is a second billed turn.
api: Dialogflow CX (v3) and Dialogflow ES (v2)
generated: '2026-09-12'
method: generated
source: openapi/google-dialogflow-cx-v3-openapi.yml, openapi/google-dialogflow-es-v2-openapi.yml, conventions/google-dialogflow-conventions.yml, rate-limits/google-dialogflow-rate-limits.yml
operations:
  - dialogflow_projects_locations_agents_sessions_detectIntent
  - dialogflow_projects_locations_agents_environments_sessions_detectIntent
  - dialogflow_projects_locations_agents_sessions_matchIntent
  - dialogflow_projects_agent_sessions_detectIntent
  - dialogflow_projects_locations_agent_sessions_detectIntent
---

# Run a conversation turn against a Dialogflow agent

This is the runtime surface. Everything else in Dialogflow is design-time.

## Before you call

- Get an OAuth 2.0 access token with scope `https://www.googleapis.com/auth/dialogflow`. There is no
  API key path. Send it as `Authorization: Bearer <token>`.
- Decide the edition. CX agents live at
  `projects/{project}/locations/{location}/agents/{agent}` and ES agents at
  `projects/{project}/agent`. They are not interchangeable and there is no cross-reference between
  them.
- For a CX agent outside the `global` location, call the regional host
  `https://{location}-dialogflow.googleapis.com`. Calling the default host for a regional agent
  returns `NOT_FOUND`, which reads like a missing agent rather than a misrouted one.

## The call

CX:

```
POST /v3/projects/{project}/locations/{location}/agents/{agent}/sessions/{session}:detectIntent
```

operationId `dialogflow_projects_locations_agents_sessions_detectIntent`.

ES:

```
POST /v2/projects/{project}/agent/sessions/{session}:detectIntent
```

operationId `dialogflow_projects_agent_sessions_detectIntent`.

To run against a pinned, deployed version instead of the draft agent, use the environment-scoped
form — `dialogflow_projects_locations_agents_environments_sessions_detectIntent` on CX, or
`dialogflow_projects_agent_environments_users_sessions_detectIntent` on ES. Do this in production;
the draft agent changes under you every time somebody edits it in the console.

## Sessions

- You choose the session id. It is an opaque string you mint, not something the API hands back.
- A session stays active for **30 minutes after the last request**, then its data is gone. There is
  no get operation for a session and no way to recover one.
- Reuse the same session id for every turn of one conversation. A new id starts a new conversation
  and loses all context and parameters.

## Rehearsing

`dialogflow_projects_locations_agents_sessions_matchIntent` returns the intents a query *would*
match without running fulfillment or advancing session state. Use it when you want to know what the
agent understands without committing the turn. It is the closest thing to a dry run this API has —
there is no `validateOnly` parameter anywhere in the contract.

## Retries — read this before writing a retry loop

Dialogflow has **no idempotency mechanism**. No `Idempotency-Key` header, no `ETag`, no `If-Match`,
on any of the 199 mutating operations. A retried `detectIntent` after a timeout is a second
conversation turn: the agent sees it, session state advances again, and you are billed again
($0.007 per Flows chat request, $0.012 per Playbooks chat request, or per second for voice).

So:

- Retry only on `UNAVAILABLE` (503), `INTERNAL` (500) and `DEADLINE_EXCEEDED` (504).
- Never retry `INVALID_ARGUMENT`, `PERMISSION_DENIED`, `NOT_FOUND` or `FAILED_PRECONDITION` — they
  will fail identically.
- On `RESOURCE_EXHAUSTED` (429), back off exactly as the SLA requires: wait 1 second after the first
  error, then double up to a 32-second ceiling. There are **no** `RateLimit-*` or `Retry-After`
  response headers to read — you cannot see remaining quota at runtime.

## Quota you will actually hit

| Surface | Limit |
|---|---|
| CX text turns | 1200 requests/minute per project |
| CX audio in/out | 600 requests/minute |
| CX generative (playbooks, data stores, generators, generative fallback) | 600,000 tokens/minute per model per region |
| ES Essentials text | 600 requests/minute |
| ES Trial text | 180 requests/minute |

Quotas are per Google Cloud **project** and shared across every application and IP using it.

## Reading the response

- A successful response carries `queryResult` with the matched intent, parameters, and the
  `responseMessages` the agent produced.
- Errors are `google.rpc.Status`, not RFC 9457 problem+json. Branch on `error.status` (the canonical
  code name, e.g. `RESOURCE_EXHAUSTED`), never on `error.message`.
- A `DEADLINE_EXCEEDED` on a turn very often means a fulfillment webhook was slow, not that
  Dialogflow was. Check the webhook before escalating.

## What you cannot undo

Nothing about a turn is reversible. There is no operation to un-send a turn, roll back session state
or refund a request. The only control is not sending it twice.
