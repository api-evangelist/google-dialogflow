---
name: google-dialogflow-webhook-fulfillment
description: Stand up and register a Dialogflow CX fulfillment webhook — the synchronous callback Dialogflow makes into your service mid-conversation — including the HTTPS, authentication and latency requirements that decide whether the turn succeeds.
api: Dialogflow CX (v3)
generated: '2026-09-12'
method: generated
source: openapi/google-dialogflow-cx-v3-openapi.yml, asyncapi/google-dialogflow-webhooks.yml, grpc/cx-v3/webhook.proto, https://cloud.google.com/dialogflow/cx/docs/concept/webhook
operations:
  - dialogflow_projects_locations_agents_webhooks_list
  - dialogflow_projects_locations_agents_webhooks_get
  - dialogflow_projects_locations_agents_webhooks_create
  - dialogflow_projects_locations_agents_webhooks_patch
  - dialogflow_projects_locations_agents_webhooks_delete
---

# Register a Dialogflow CX fulfillment webhook

## Understand what this is before you build it

This is not a notification webhook. Dialogflow calls your endpoint **in the middle of a
conversation turn and waits for your answer** before it can respond to the end user. Your latency is
the user's latency, and your failure is the turn's failure — a slow endpoint surfaces to the API
caller as `DEADLINE_EXCEEDED` (504). Treat it as a synchronous RPC you happen to receive over HTTP.

## Webhooks are API resources

Unusually, CX makes the webhook configuration a first-class resource, so you can enumerate and
reconfigure the event surface programmatically instead of clicking through a dashboard:

- `dialogflow_projects_locations_agents_webhooks_list`
- `dialogflow_projects_locations_agents_webhooks_get`
- `dialogflow_projects_locations_agents_webhooks_create`
- `dialogflow_projects_locations_agents_webhooks_patch` (send `updateMask` — see below)
- `dialogflow_projects_locations_agents_webhooks_delete`

Limit: **100 webhooks per agent**.

## Requirements your service must meet

- **HTTPS only.** Plain HTTP is unsupported.
- The URL must be publicly reachable, unless it is a Cloud Run resource or is reached through
  Service Directory private network access.
- If the agent does not integrate with Service Directory private network access, webhook calls sit
  **outside** the VPC Service Controls perimeter and are **blocked** when VPC-SC is enabled. This is
  the single most common surprise when a team turns on VPC-SC.

## Choose a webhook subtype

- **Standard** — Dialogflow owns the request and response shape (`WebhookRequest` /
  `WebhookResponse`). The message definitions are first-party protobuf; this repo mirrors them
  verbatim at `grpc/cx-v3/webhook.proto`. Generate your handler types from there rather than
  hand-writing them.
- **Flexible** — you define the request body JSON and map fields out of the response, which lets CX
  call a third-party API directly without a shim service.

## Authentication

Configure it on the webhook resource. Supported mechanisms:

- **Authentication headers** — arbitrary key/value pairs; commonly a single `authorization` header.
  Values support session-parameter references and system functions. Supply static credentials
  through Secret Manager, not inline.
- **Basic auth** — Dialogflow sends `authorization: Basic <base64 of username:password>`.
- **Third-party OAuth** — configured on the webhook resource.
- **Service account authorization** — added 2025-10-23, available for both tools and webhooks.
- **Mutual TLS**.

**Do not use service agent access tokens.** They were discontinued; Google announced it in the
2025-06-12 release note after emailing affected customers.

Also note the 2025-12-11 security entry: the CX Messenger integration had an authentication-bypass
flaw when an agent used an authenticated API with a third-party identity. Builds after 2025-08-20
are patched, and since the Messenger loader URL is unpinned
(`.../df-messenger/prod/v1/df-messenger.js`) everybody was moved automatically — which also means
you cannot pin a known-good build.

## Updating a webhook

`dialogflow_projects_locations_agents_webhooks_patch` obeys the same rule as every other Dialogflow
PATCH: **send `updateMask`**. Without it, the request body replaces the whole webhook resource,
including its authentication configuration.

## Operational notes

- There is no idempotency key on webhook management or on the turn itself. If Dialogflow retries a
  turn, your handler will see the request again — make your side effects safe to repeat, because
  the API will not do it for you.
- Deleting a webhook that pages still reference fails with `FAILED_PRECONDITION` unless you pass
  `force`. `force` is not reversible; there is no undelete.
- Test the whole path with test cases (`dialogflow_projects_locations_agents_testCases_run`) rather
  than with live turns — but remember test-case runs execute real agent turns and are billed and
  quota'd like any other.
