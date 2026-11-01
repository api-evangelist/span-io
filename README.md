# SPAN

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

SPAN is a San Francisco-based home energy technology company building smart electrical panels that replace traditional residential breaker boxes with a software-defined, controllable, and metered panel. SPAN Panel provides whole-home real-time power and energy metering, per-circuit monitoring and remote relay control, grid/islanding state management for whole-home backup with solar and energy storage, EV charging coordination via SPAN Drive, and a mobile app for energy management. As of the SPAN Panel firmware r202603 release (Q1 2026), SPAN exposes a public-beta on-premise SPAN API for software integrations between SPAN Panel and other devices on the home Local Area Network. The SPAN API is a real, documented HTTP + MQTT/Homie surface that runs directly on the panel — there is no cloud-hosted developer endpoint. The REST surface provides authentication, system status, Wi-Fi setup, panel state, per-circuit control, panel grid relay, energy storage state-of-energy, and emergency reconnect operations. The publish/subscribe surface uses the Electrification Bus (eBus) framework and Homie Convention over MQTT for streaming real-time panel state, per-circuit telemetry, and control of relays. SPAN API is licensed for personal, non-commercial use under MIT-0 for docs and example code; commercial / fleet use requires the separately licensed SPAN Fleet Manager.

**Areas:** Energy · Home Energy · Electrification · Smart Panel · Electrical Panel · Home Automation · Solar · Energy Storage · EV Charging · Grid · Islanding · Backup Power

## SPAN on APIs.io

Everything profiled for SPAN is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/span-io/](https://apis.io/providers/span-io/)** — or go straight to one of the APIs or properties below.

### APIs (9)

- [SPAN eBus MQTT API](https://apis.io/apis/span-io/span-ebus-mqtt-api/) — Publish/subscribe streaming API hosted on SPAN Panel using the Electrification Bus (eBus) integration framework and the Homie Convention. SPAN Panel hosts…
- [SPAN Auth API](https://apis.io/apis/span-io/span-io-auth-api/) — The Auth API from SPAN — 3 operation(s) for auth.
- [SPAN Circuits API](https://apis.io/apis/span-io/span-io-circuits-api/) — The Circuits API from SPAN — 2 operation(s) for circuits.
- [SPAN Islanding State API](https://apis.io/apis/span-io/span-io-islanding-state-api/) — The Islanding State API from SPAN — 1 operation(s) for islanding state.
- [SPAN Panel API](https://apis.io/apis/span-io/span-io-panel-api/) — The Panel API from SPAN — 5 operation(s) for panel.
- [SPAN Spaces API](https://apis.io/apis/span-io/span-io-spaces-api/) — The Spaces API from SPAN — 2 operation(s) for spaces.
- [SPAN Status API](https://apis.io/apis/span-io/span-io-status-api/) — The Status API from SPAN — 1 operation(s) for status.
- [SPAN Storage API](https://apis.io/apis/span-io/span-io-storage-api/) — The Storage API from SPAN — 2 operation(s) for storage.
- [SPAN Wifi API](https://apis.io/apis/span-io/span-io-wifi-api/) — The Wifi API from SPAN — 2 operation(s) for wifi.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [SPAN eBus MQTT API](https://apis.io/asyncapis/span-io/span-ebus-asyncapi/)

#### Event channels (11)

Individual events and webhooks the provider emits.

- [ebus/5/{serial}/circuits/{circuitId}/power](https://apis.io/channels/span-io/ebus-5-serial-circuits-circuitid-power/)
- [ebus/5/{serial}/circuits/{circuitId}/relay-state](https://apis.io/channels/span-io/ebus-5-serial-circuits-circuitid-relay-state/)
- [ebus/5/{serial}/circuits/{circuitId}/relay-state/set](https://apis.io/channels/span-io/ebus-5-serial-circuits-circuitid-relay-state-set/)
- [ebus/5/{serial}/$description](https://apis.io/channels/span-io/ebus-5-serial-description/)
- [ebus/5/{serial}/panel/grid](https://apis.io/channels/span-io/ebus-5-serial-panel-grid/)
- [ebus/5/{serial}/panel/grid/set](https://apis.io/channels/span-io/ebus-5-serial-panel-grid-set/)
- [ebus/5/{serial}/panel/islanding-state](https://apis.io/channels/span-io/ebus-5-serial-panel-islanding-state/)
- [ebus/5/{serial}/panel/meter](https://apis.io/channels/span-io/ebus-5-serial-panel-meter/)
- [ebus/5/{serial}/panel/power](https://apis.io/channels/span-io/ebus-5-serial-panel-power/)
- [ebus/5/{serial}/$state](https://apis.io/channels/span-io/ebus-5-serial-state/)
- [ebus/5/{serial}/storage/soe](https://apis.io/channels/span-io/ebus-5-serial-storage-soe/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Span Io Agentic Access](https://apis.io/agentic-access/span-io/span-io-agentic-access/)

#### JSON Schema (2)

The data models the API reads and writes.

- [Span Homie](https://apis.io/schemas/span-io/span-homie/)
- [Span Mdns Services](https://apis.io/schemas/span-io/span-mdns-services/)

#### JSON-LD (1)

Linked-data contexts for the provider's vocabulary.

- [Span Context](https://apis.io/jsonld/span-io/span-context/)

#### Vocabulary (1)

The provider's domain terms, defined.

- [SPAN Vocabulary](https://apis.io/vocabularies/span-io/span-io-vocabulary/)

#### Collections (9)

Postman and Open Collection request collections.

- [Span Auth API](https://apis.io/collections/span-io/open-span-io-auth-api/)
- [Span Auth Circuits API](https://apis.io/collections/span-io/open-span-io-circuits-api/)
- [Span Auth Islanding State API](https://apis.io/collections/span-io/open-span-io-islanding-state-api/)
- [Span Auth Panel API](https://apis.io/collections/span-io/open-span-io-panel-api/)
- [Span Auth Spaces API](https://apis.io/collections/span-io/open-span-io-spaces-api/)
- [Span Auth Status API](https://apis.io/collections/span-io/open-span-io-status-api/)
- [Span Auth Storage API](https://apis.io/collections/span-io/open-span-io-storage-api/)
- [Span Auth Wifi API](https://apis.io/collections/span-io/open-span-io-wifi-api/)
- [Span](https://apis.io/collections/span-io/open-span-rest-api/)

#### Governance rules (2)

Spectral rulesets for the provider's contracts.

- [SPAN — asyncapi rules](https://apis.io/rules/span-io/span-io-asyncapi-spectral-rules/)
- [SPAN API Rules](https://apis.io/rules/span-io/span-io-rules/)

#### Security (3)

Authentication, trust centre, and vulnerability disclosure.

- [Span Io Authentication](https://apis.io/security/span-io/span-io-authentication/)
- [Span Io Domain Security](https://apis.io/security/span-io/span-io-domain-security/)
- [Span Io Vulnerability Disclosure](https://apis.io/security/span-io/span-io-vulnerability-disclosure/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Span Io Plans Pricing](https://apis.io/plans/span-io/span-io-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Span Io Rate Limits](https://apis.io/rate-limits/span-io/span-io-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Span Io Finops](https://apis.io/finops/span-io/span-io-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.span.io)
- [Documentation](https://github.com/spanio/SPAN-API-Client-Docs)
- [Support](https://support.span.io/hc/en-us)
- [Changelog](https://github.com/spanio/SPAN-API-Client-Docs/blob/main/CHANGELOG.md)
- [Blog](https://www.span.io/blog)
- [Terms of service](https://www.span.io/terms-of-service)
- [Privacy policy](https://www.span.io/privacy-policy)
- [GitHub](https://github.com/spanio)

## API Evangelist rating

**Kin Score 38.7** — thin · rubric 0.24.0 · scored 2026-10-17

| Facet | Score |
|---|---|
| Discoverability | 57.1 |
| Contract quality | 56.9 |
| Contract governance | 13.6 |
| Operational transparency | 18.4 |
| Developer ergonomics | 52.4 |
| Access clarity | 18.4 |

**Agent readiness 24.7** — agent-aware

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | verified |
| OpenAPI Examples | — |
| Rate Limit Signal | derived (partial credit) |
| Event Surface Described | derived (partial credit) |
| Agent Skills | — |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |

**Regulatory alignment 22.1** — Energy & Utilities

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/span-io/](https://apis.io/providers/span-io/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for SPAN: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/span-io/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
