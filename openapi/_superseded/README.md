# Superseded OpenAPI definitions

These two files were in the repo before 2026-09-12. Between them they described **9 operations**
of Dialogflow ES v2. They carried no recorded fetch URL, and Google publishes no OpenAPI for
Dialogflow, so their origin could not be re-verified.

They were superseded on 2026-09-12 by two definitions converted mechanically from Google's own
first-party Discovery Documents, served live by the API host:

| File | Source | Operations |
|---|---|---|
| `../google-dialogflow-es-v2-openapi.yml` | `https://dialogflow.googleapis.com/$discovery/rest?version=v2` (revision 20260825) | 279 |
| `../google-dialogflow-cx-v3-openapi.yml` | `https://dialogflow.googleapis.com/$discovery/rest?version=v3` (revision 20260825) | 158 |

The raw Discovery Documents themselves are kept verbatim in `../../discovery/`.
Nothing here is referenced by `apis.yml` any more; the files are retained only for audit.
