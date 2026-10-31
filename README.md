# Google Dialogflow

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Google Dialogflow is Google Cloud's conversational-agent platform, shipped as two editions on one API host. Dialogflow ES (Essentials, API v2) builds intent-, entity- and context-driven agents with knowledge connectors and the Agent Assist surface for human contact-centre agents. Dialogflow CX — now branded Conversational Agents, API v3 — builds flow-based state-machine agents and generative playbook agents backed by Gemini models, data stores, generators and tool calling, with test cases, experiments, versions and environments as first-class API resources. Both are called at dialogflow.googleapis.com with a Google OAuth 2.0 bearer token; there is no API key. Google publishes no OpenAPI for Dialogflow — the first-party machine-readable contracts are the Google Discovery Documents served by the API host itself (279 operations on v2, 158 on v3) and the protobuf IDL in googleapis/googleapis (42 gRPC services, 267 RPCs).

**Areas:** Agents · Artificial Intelligence · Chatbots · Conversational AI · Google Cloud · Machine Learning · Natural Language Processing · Speech Recognition · Virtual Agents · Voice Assistant

## Google Dialogflow on APIs.io

Everything profiled for Google Dialogflow is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/google-dialogflow/](https://apis.io/providers/google-dialogflow/)** — or go straight to one of the APIs or properties below.

### APIs (42)

- [Dialogflow](https://apis.io/apis/google-dialogflow/dialogflow/) — Natural Language Processing
- [Google Dialogflow Agent API](https://apis.io/apis/google-dialogflow/google-dialogflow-agent-api/) — The agent API from Google Dialogflow — 14 operation(s) for agent.
- [Google Dialogflow Agents API](https://apis.io/apis/google-dialogflow/google-dialogflow-agents-api/) — The agents API from Google Dialogflow — 7 operation(s) for agents.
- [Google Dialogflow Answer Records API](https://apis.io/apis/google-dialogflow/google-dialogflow-answerrecords-api/) — The answerRecords API from Google Dialogflow — 4 operation(s) for answerrecords.
- [Google Dialogflow Changelogs API](https://apis.io/apis/google-dialogflow/google-dialogflow-changelogs-api/) — The changelogs API from Google Dialogflow — 2 operation(s) for changelogs.
- [Google Dialogflow Contexts API](https://apis.io/apis/google-dialogflow/google-dialogflow-contexts-api/) — The contexts API from Google Dialogflow — 8 operation(s) for contexts.
- [Google Dialogflow Continuous Test Results API](https://apis.io/apis/google-dialogflow/google-dialogflow-continuoustestresults-api/) — The continuousTestResults API from Google Dialogflow — 1 operation(s) for continuoustestresults.
- [Google Dialogflow Conversation Datasets API](https://apis.io/apis/google-dialogflow/google-dialogflow-conversationdatasets-api/) — The conversationDatasets API from Google Dialogflow — 6 operation(s) for conversationdatasets.
- [Google Dialogflow Conversation Models API](https://apis.io/apis/google-dialogflow/google-dialogflow-conversationmodels-api/) — The conversationModels API from Google Dialogflow — 8 operation(s) for conversationmodels.
- [Google Dialogflow Conversation Profiles API](https://apis.io/apis/google-dialogflow/google-dialogflow-conversationprofiles-api/) — The conversationProfiles API from Google Dialogflow — 8 operation(s) for conversationprofiles.
- [Google Dialogflow Conversations API](https://apis.io/apis/google-dialogflow/google-dialogflow-conversations-api/) — The conversations API from Google Dialogflow — 7 operation(s) for conversations.
- [Google Dialogflow Deployments API](https://apis.io/apis/google-dialogflow/google-dialogflow-deployments-api/) — The deployments API from Google Dialogflow — 2 operation(s) for deployments.
- [Google Dialogflow Documents API](https://apis.io/apis/google-dialogflow/google-dialogflow-documents-api/) — The documents API from Google Dialogflow — 13 operation(s) for documents.
- [Google Dialogflow Encryption Spec API](https://apis.io/apis/google-dialogflow/google-dialogflow-encryptionspec-api/) — The encryptionSpec API from Google Dialogflow — 1 operation(s) for encryptionspec.
- [Google Dialogflow Entities API](https://apis.io/apis/google-dialogflow/google-dialogflow-entities-api/) — The entities API from Google Dialogflow — 6 operation(s) for entities.
- [Google Dialogflow Environments API](https://apis.io/apis/google-dialogflow/google-dialogflow-environments-api/) — The environments API from Google Dialogflow — 11 operation(s) for environments.
- [Google Dialogflow Evaluations API](https://apis.io/apis/google-dialogflow/google-dialogflow-evaluations-api/) — The evaluations API from Google Dialogflow — 6 operation(s) for evaluations.
- [Google Dialogflow Examples API](https://apis.io/apis/google-dialogflow/google-dialogflow-examples-api/) — The examples API from Google Dialogflow — 2 operation(s) for examples.
- [Google Dialogflow Experiments API](https://apis.io/apis/google-dialogflow/google-dialogflow-experiments-api/) — The experiments API from Google Dialogflow — 4 operation(s) for experiments.
- [Google Dialogflow Flows API](https://apis.io/apis/google-dialogflow/google-dialogflow-flows-api/) — The flows API from Google Dialogflow — 7 operation(s) for flows.
- [Google Dialogflow Generators API](https://apis.io/apis/google-dialogflow/google-dialogflow-generators-api/) — The generators API from Google Dialogflow — 5 operation(s) for generators.
- [Google Dialogflow Intents API](https://apis.io/apis/google-dialogflow/google-dialogflow-intents-api/) — The intents API from Google Dialogflow — 14 operation(s) for intents.
- [Google Dialogflow Locations API](https://apis.io/apis/google-dialogflow/google-dialogflow-locations-api/) — The locations API from Google Dialogflow — 6 operation(s) for locations.
- [Google Dialogflow Messages API](https://apis.io/apis/google-dialogflow/google-dialogflow-messages-api/) — The messages API from Google Dialogflow — 2 operation(s) for messages.
- [Google Dialogflow Operations API](https://apis.io/apis/google-dialogflow/google-dialogflow-operations-api/) — The operations API from Google Dialogflow — 12 operation(s) for operations.
- [Google Dialogflow Pages API](https://apis.io/apis/google-dialogflow/google-dialogflow-pages-api/) — The pages API from Google Dialogflow — 2 operation(s) for pages.
- [Google Dialogflow Participants API](https://apis.io/apis/google-dialogflow/google-dialogflow-participants-api/) — The participants API from Google Dialogflow — 6 operation(s) for participants.
- [Google Dialogflow Playbooks API](https://apis.io/apis/google-dialogflow/google-dialogflow-playbooks-api/) — The playbooks API from Google Dialogflow — 4 operation(s) for playbooks.
- [Google Dialogflow Projects API](https://apis.io/apis/google-dialogflow/google-dialogflow-projects-api/) — The projects API from Google Dialogflow — 1 operation(s) for projects.
- [Google Dialogflow Results API](https://apis.io/apis/google-dialogflow/google-dialogflow-results-api/) — The results API from Google Dialogflow — 2 operation(s) for results.
- [Google Dialogflow Sessions API](https://apis.io/apis/google-dialogflow/google-dialogflow-sessions-api/) — The sessions API from Google Dialogflow — 17 operation(s) for sessions.
- [Google Dialogflow Stateless Suggestion API](https://apis.io/apis/google-dialogflow/google-dialogflow-statelesssuggestion-api/) — The statelessSuggestion API from Google Dialogflow — 1 operation(s) for statelesssuggestion.
- [Google Dialogflow Suggestions API](https://apis.io/apis/google-dialogflow/google-dialogflow-suggestions-api/) — The suggestions API from Google Dialogflow — 18 operation(s) for suggestions.
- [Google Dialogflow Tools API](https://apis.io/apis/google-dialogflow/google-dialogflow-tools-api/) — The tools API from Google Dialogflow — 4 operation(s) for tools.
- [Google Dialogflow Transition Route Groups API](https://apis.io/apis/google-dialogflow/google-dialogflow-transitionroutegroups-api/) — The transitionRouteGroups API from Google Dialogflow — 4 operation(s) for transitionroutegroups.
- [Google Dialogflow Versions API](https://apis.io/apis/google-dialogflow/google-dialogflow-versions-api/) — The versions API from Google Dialogflow — 14 operation(s) for versions.
- [Google Dialogflow Webhooks API](https://apis.io/apis/google-dialogflow/google-dialogflow-webhooks-api/) — The webhooks API from Google Dialogflow — 2 operation(s) for webhooks.
- [Google Dialogflow Entity Types API](https://apis.io/apis/google-dialogflow/google-dialogflow-entity-types-api/) — The Entity Types API from Google Dialogflow — 24 operation(s) for entity types.
- [Google Dialogflow Knowledge Bases API](https://apis.io/apis/google-dialogflow/google-dialogflow-knowledge-bases-api/) — The Knowledge Bases API from Google Dialogflow — 6 operation(s) for knowledge bases.
- [Google Dialogflow Security Settings API](https://apis.io/apis/google-dialogflow/google-dialogflow-security-settings-api/) — The Security Settings API from Google Dialogflow — 2 operation(s) for security settings.
- [Google Dialogflow SIP Trunks API](https://apis.io/apis/google-dialogflow/google-dialogflow-sip-trunks-api/) — The SIP Trunks API from Google Dialogflow — 2 operation(s) for sip trunks.
- [Google Dialogflow Test Cases API](https://apis.io/apis/google-dialogflow/google-dialogflow-test-cases-api/) — The Test Cases API from Google Dialogflow — 8 operation(s) for test cases.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Google Dialogflow Webhooks](https://apis.io/asyncapis/google-dialogflow/google-dialogflow-webhooks/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [google-dialogflow-mcp.yml](https://apis.io/servers/google-dialogflow/google-dialogflow-mcp-yml/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Google Dialogflow Agentic Access](https://apis.io/agentic-access/google-dialogflow/google-dialogflow-agentic-access/)

#### Collections (2)

Postman and Open Collection request collections.

- [Dialogflow ES API](https://apis.io/collections/google-dialogflow/open-google-dialogflow/)
- [Dialogflow ES Projects API](https://apis.io/collections/google-dialogflow/open-google-dialogflow-projects-api/)

#### Overlays (43)

OpenAPI overlays, including conversational phrasing for each operation.

- [Google Dialogflow Agent Api Phrasing Overlay](https://apis.io/overlays/google-dialogflow/google-dialogflow-agent-api-phrasing-overlay/)
- [Google Dialogflow Agents Api Phrasing Overlay](https://apis.io/overlays/google-dialogflow/google-dialogflow-agents-api-phrasing-overlay/)
- [Google Dialogflow Answerrecords Api Phrasing Overlay](https://apis.io/overlays/google-dialogflow/google-dialogflow-answerrecords-api-phrasing-overlay/)
- [Google Dialogflow Changelogs Api Phrasing Overlay](https://apis.io/overlays/google-dialogflow/google-dialogflow-changelogs-api-phrasing-overlay/)
- [Google Dialogflow Contexts Api Phrasing Overlay](https://apis.io/overlays/google-dialogflow/google-dialogflow-contexts-api-phrasing-overlay/)
- [Google Dialogflow Continuoustestresults Api Phrasing Overlay](https://apis.io/overlays/google-dialogflow/google-dialogflow-continuoustestresults-api-phrasing-overlay/)
- [Google Dialogflow Conversationdatasets Api Phrasing Overlay](https://apis.io/overlays/google-dialogflow/google-dialogflow-conversationdatasets-api-phrasing-overlay/)
- [Google Dialogflow Conversationmodels Api Phrasing Overlay](https://apis.io/overlays/google-dialogflow/google-dialogflow-conversationmodels-api-phrasing-overlay/)
- [Google Dialogflow Conversationprofiles Api Phrasing Overlay](https://apis.io/overlays/google-dialogflow/google-dialogflow-conversationprofiles-api-phrasing-overlay/)
- [Google Dialogflow Conversations Api Phrasing Overlay](https://apis.io/overlays/google-dialogflow/google-dialogflow-conversations-api-phrasing-overlay/)
- [Google Dialogflow Cx V3 Overlay](https://apis.io/overlays/google-dialogflow/google-dialogflow-cx-v3-overlay/)
- [Google Dialogflow Deployments Api Phrasing Overlay](https://apis.io/overlays/google-dialogflow/google-dialogflow-deployments-api-phrasing-overlay/)
- [Google Dialogflow Documents Api Phrasing Overlay](https://apis.io/overlays/google-dialogflow/google-dialogflow-documents-api-phrasing-overlay/)
- [Google Dialogflow Encryptionspec Api Phrasing Overlay](https://apis.io/overlays/google-dialogflow/google-dialogflow-encryptionspec-api-phrasing-overlay/)
- [Google Dialogflow Entities Api Phrasing Overlay](https://apis.io/overlays/google-dialogflow/google-dialogflow-entities-api-phrasing-overlay/)
- [Google Dialogflow Entity Types Api Phrasing Overlay](https://apis.io/overlays/google-dialogflow/google-dialogflow-entity-types-api-phrasing-overlay/)
- [Google Dialogflow Environments Api Phrasing Overlay](https://apis.io/overlays/google-dialogflow/google-dialogflow-environments-api-phrasing-overlay/)
- [Google Dialogflow Es V2 Overlay](https://apis.io/overlays/google-dialogflow/google-dialogflow-es-v2-overlay/)
- [Google Dialogflow Evaluations Api Phrasing Overlay](https://apis.io/overlays/google-dialogflow/google-dialogflow-evaluations-api-phrasing-overlay/)
- [Google Dialogflow Examples Api Phrasing Overlay](https://apis.io/overlays/google-dialogflow/google-dialogflow-examples-api-phrasing-overlay/)
- [Google Dialogflow Experiments Api Phrasing Overlay](https://apis.io/overlays/google-dialogflow/google-dialogflow-experiments-api-phrasing-overlay/)
- [Google Dialogflow Flows Api Phrasing Overlay](https://apis.io/overlays/google-dialogflow/google-dialogflow-flows-api-phrasing-overlay/)
- [Google Dialogflow Generators Api Phrasing Overlay](https://apis.io/overlays/google-dialogflow/google-dialogflow-generators-api-phrasing-overlay/)
- [Google Dialogflow Intents Api Phrasing Overlay](https://apis.io/overlays/google-dialogflow/google-dialogflow-intents-api-phrasing-overlay/)
- [Google Dialogflow Knowledge Bases Api Phrasing Overlay](https://apis.io/overlays/google-dialogflow/google-dialogflow-knowledge-bases-api-phrasing-overlay/)
- …and 18 more published on APIs.io

#### Security (3)

Authentication, trust centre, and vulnerability disclosure.

- [Google Dialogflow Authentication](https://apis.io/security/google-dialogflow/google-dialogflow-authentication/)
- [Google Dialogflow Domain Security](https://apis.io/security/google-dialogflow/google-dialogflow-domain-security/)
- [Google Dialogflow Vulnerability Disclosure](https://apis.io/security/google-dialogflow/google-dialogflow-vulnerability-disclosure/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Google Dialogflow Scopes](https://apis.io/scopes/google-dialogflow/google-dialogflow-scopes/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Google Dialogflow Plans Pricing](https://apis.io/plans/google-dialogflow/google-dialogflow-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Google Dialogflow Rate Limits](https://apis.io/rate-limits/google-dialogflow/google-dialogflow-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Google Dialogflow Finops](https://apis.io/finops/google-dialogflow/google-dialogflow-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://cloud.google.com/dialogflow)
- [Documentation](https://cloud.google.com/dialogflow/docs)
- [Getting started](https://cloud.google.com/dialogflow/es/docs/quick/setup)
- [API reference](https://cloud.google.com/dialogflow/docs/reference/rest)
- [Pricing](https://cloud.google.com/dialogflow/pricing)
- [Sign up](https://console.cloud.google.com/freetrial)
- [Support](https://cloud.google.com/dialogflow/docs/support)
- [Blog](https://cloud.google.com/blog/products/ai-machine-learning)
- [Compliance](https://cloud.google.com/dialogflow/docs/compliance-security-controls)
- [Terms of service](https://cloud.google.com/terms)
- [Privacy policy](https://policies.google.com/privacy)
- [GitHub](https://github.com/googleapis)
- [Status](https://status.cloud.google.com/)

## API Evangelist rating

**Kin Score 66.1** — strong · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 66.1 |
| Contract quality | 54.2 |
| Contract governance | 18.2 |
| Operational transparency | 92.1 |
| Developer ergonomics | 73.2 |
| Access clarity | 71.1 |

**Agent readiness 38.2** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | documented (partial credit) |
| MCP Server | — |
| Auth Clarity | served (partial credit) |
| Idempotency | — |
| Error Semantics | derived (partial credit) |
| OpenAPI Examples | — |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | yes |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | served (partial credit) |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | paginated |
| Operation Distinctiveness | mostly (partial credit) |

**Regulatory alignment 41.8** — AI & Biometrics

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/google-dialogflow/](https://apis.io/providers/google-dialogflow/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Google Dialogflow: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/google-dialogflow/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
