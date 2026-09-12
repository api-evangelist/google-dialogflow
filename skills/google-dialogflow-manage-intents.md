---
name: google-dialogflow-manage-intents
description: Create, read, update and delete Dialogflow intents and entity types safely — the design-time authoring flow, where the 60-requests-per-minute write quota and the updateMask rule decide whether you succeed or quietly destroy an intent.
api: Dialogflow CX (v3) and Dialogflow ES (v2)
generated: '2026-09-12'
method: generated
source: openapi/google-dialogflow-cx-v3-openapi.yml, openapi/google-dialogflow-es-v2-openapi.yml, conventions/google-dialogflow-conventions.yml, rate-limits/google-dialogflow-rate-limits.yml
operations:
  - dialogflow_projects_locations_agents_intents_list
  - dialogflow_projects_locations_agents_intents_get
  - dialogflow_projects_locations_agents_intents_create
  - dialogflow_projects_locations_agents_intents_patch
  - dialogflow_projects_locations_agents_intents_delete
  - dialogflow_projects_agent_intents_list
  - dialogflow_projects_agent_intents_create
  - dialogflow_projects_agent_intents_patch
  - dialogflow_projects_agent_intents_batchUpdate
  - dialogflow_projects_locations_agents_entityTypes_list
  - dialogflow_projects_locations_agents_entityTypes_create
  - dialogflow_projects_locations_agents_entityTypes_patch
---

# Author a Dialogflow agent's intents and entity types

## The one rule that matters most

Every `PATCH` in Dialogflow takes an `updateMask` query parameter, and **all 53 of them
(33 in ES v2, 20 in CX v3) behave the same way**: if you omit `updateMask`, the request body
replaces the entire resource. Send an intent body with only `displayName` set and no mask, and you
have just deleted every training phrase on that intent.

Always send `updateMask` naming exactly the fields you are changing:

```
PATCH /v3/projects/{p}/locations/{l}/agents/{a}/intents/{i}?updateMask=displayName,trainingPhrases
```

## List, then act

Start with `dialogflow_projects_locations_agents_intents_list` (CX) or
`dialogflow_projects_agent_intents_list` (ES). Both paginate with `pageSize` + `pageToken` in and
`nextPageToken` out; an absent token means the last page.

Resolve the full resource name from the list before any get, patch or delete. Dialogflow ids are
opaque and unprefixed — an id on its own tells you nothing about what it is. Only the full
hierarchical name does.

## Creating

`dialogflow_projects_locations_agents_intents_create` (CX) /
`dialogflow_projects_agent_intents_create` (ES).

There is no idempotency key. If your create times out and you retry, you get a second intent — or
`ALREADY_EXISTS` if `displayName` collides. Read the list first and treat an existing equivalent
intent as success rather than blindly retrying.

For bulk work on ES, `dialogflow_projects_agent_intents_batchUpdate` takes many intents in one call
and returns a long-running operation. Prefer it over a loop: it is one request against the 60/minute
design-time write quota instead of N.

## The quota that will stop you

Design-time writes are capped at **60 requests per minute** per project, on both editions. That is
the real ceiling on any agent doing bulk authoring — one write per second, sustained. Design-time
reads are 300/minute on CX and 60/minute on ES.

Plan for it: batch where a batch operation exists, and pace the rest. On `RESOURCE_EXHAUSTED` back
off 1 second, doubling to 32 seconds. No rate-limit headers are returned.

## Fixed limits you cannot raise

| | CX | ES |
|---|---|---|
| Intents per agent | 10,000 | 2,000 |
| Entity types per agent | 250 | 250 |
| Training phrases per intent per language | 2,000 | 2,000 |
| Training phrases per agent/flow per language | 100,000 | 100,000 |
| Entity entries per entity type | 30,000 | 30,000 |
| Parameters per intent | 20 | 20 |

These are limits, not quotas — a support request will not raise them.

## Deleting

`dialogflow_projects_locations_agents_intents_delete`. Some delete operations accept a `force`
parameter (3 operations in v2, 9 in v3) which cascades the delete to resources that reference the
target. Without it you get `FAILED_PRECONDITION` when something still points at it.

**There is no undelete.** No restore operation exists for an intent, entity type, page or flow. The
only recovery path is a whole-agent restore from an export you took yourself
(`dialogflow_projects_agent_export` then `dialogflow_projects_agent_restore`), and Google states no
retention window for that — the window is however long you kept the file.

Take an export before any bulk delete.

## After authoring

- ES agents must be retrained before the changes take effect at runtime:
  `dialogflow_projects_agent_train` (a long-running operation — poll it).
- CX: validate with `dialogflow_projects_locations_agents_validate` and
  `dialogflow_projects_locations_agents_flows_validate`, then run your test cases
  (`dialogflow_projects_locations_agents_testCases_batchRun`) before promoting a version.
