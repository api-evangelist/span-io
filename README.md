# SPAN (span-io)

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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

SPAN is a San Francisco-based home energy technology company building smart electrical panels that replace traditional residential breaker boxes with a software-defined, controllable, and metered panel. SPAN Panel provides whole-home real-time power and energy metering, per-circuit monitoring and remote relay control, grid/islanding state management for whole-home backup with solar and energy storage, EV charging coordination via SPAN Drive, and a mobile app for energy management. As of the SPAN Panel firmware r202603 release (Q1 2026), SPAN exposes a public-beta on-premise SPAN API for software integrations between SPAN Panel and other devices on the home Local Area Network. The SPAN API is a real, documented HTTP + MQTT/Homie surface that runs directly on the panel — there is no cloud-hosted developer endpoint. The REST surface provides authentication, system status, Wi-Fi setup, panel state, per-circuit control, panel grid relay, energy storage state-of-energy, and emergency reconnect operations. The publish/subscribe surface uses the Electrification Bus (eBus) framework and Homie Convention over MQTT for streaming real-time panel state, per-circuit telemetry, and control of relays. SPAN API is licensed for personal, non-commercial use under MIT-0 for docs and example code; commercial / fleet use requires the separately licensed SPAN Fleet Manager.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/span-io/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/span-io/refs/heads/main/apis.yml)

## Scope

- **Type:** Provider
- **Position:** Provider
- **Access:** 3rd-Party

## Tags

- Energy
- Home Energy
- Electrification
- Smart Panel
- Electrical Panel
- Home Automation
- Solar
- Energy Storage
- EV Charging
- Grid
- Islanding
- Backup Power
- Demand Response
- IoT
- MQTT
- Homie
- Electrification Bus
- On-Premise

## Timestamps

- **Created:** 2026-05-25
- **Modified:** 2026-05-25

## APIs

### SPAN REST API

Local on-premise HTTP/JSON REST API hosted directly on SPAN Panel. The API exposes authentication (registering API clients and obtaining JWT access tokens), system status, Wi-Fi scan and connect, panel state, main meter, panel power, islanding state, per-circuit control, panel grid relay control, emergency reconnect, and energy storage state-of-energy and nice-to-have thresholds. All access is local-only on the home LAN; authentication uses HTTP Bearer JWT credentials minted by the panel itself. Available initially on SPAN Panel MAIN 32 with firmware r202603 and later, with rollout to MAIN 16 / MLO 24 / MAIN 40 / MLO 48 planned for the second half of 2026.

- **Human URL:** [https://github.com/spanio/SPAN-API-Client-Docs](https://github.com/spanio/SPAN-API-Client-Docs)
- **Base URL:** `http://span-{serial-number}.local/api/v1`

#### Tags

- Energy
- Home Energy
- Smart Panel
- REST
- On-Premise
- Circuits
- Energy Storage
- Grid
- Islanding

#### Properties

- [Documentation](https://github.com/spanio/SPAN-API-Client-Docs)
- [Documentation](https://github.com/spanio/SPAN-API-Client-Docs/blob/main/README.md)
- [OpenAPI](openapi/span-rest-api-openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/span-rest-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/span-rest-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [OpenAPI](https://github.com/spanio/SPAN-API-Client-Docs/blob/main/specs/r202615/openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [JSON Schema](json-schema/span-mdns-services-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON-LD](json-ld/span-context.jsonld) — [JSON-LD](https://www.w3.org/TR/json-ld11/)

### SPAN eBus MQTT API

Publish/subscribe streaming API hosted on SPAN Panel using the Electrification Bus (eBus) integration framework and the Homie Convention. SPAN Panel hosts an MQTT broker accessible over MQTTS (8883), WS, and WSS. Clients subscribe to `ebus/5/<serial>/...` topics to receive real-time panel state, per-circuit telemetry, energy storage state, and SPAN Drive integration data, and publish to `/set` topics to operate relays and control panel state. The broker enforces topic-level ACLs — full read access on `ebus/#`, write access limited to Homie `/set` control topics and to non-panel device subtrees under `ebus/5/`. Credentials are obtained via the REST authentication endpoint.

- **Human URL:** [https://github.com/spanio/SPAN-API-Client-Docs#span-api-interaction-models](https://github.com/spanio/SPAN-API-Client-Docs#span-api-interaction-models)

#### Tags

- MQTT
- Homie
- Electrification Bus
- eBus
- Pub/Sub
- Streaming
- On-Premise
- Energy

#### Properties

- [Documentation](https://github.com/spanio/SPAN-API-Client-Docs#publishsubscribe)
- [Documentation](https://homieiot.github.io/specification/)
- [Documentation](https://ebus.energy/)
- [AsyncAPI](asyncapi/span-ebus-asyncapi.yml) — [AsyncAPI Specification](https://www.asyncapi.com/docs/reference/specification/latest)
- [JSON Schema](json-schema/span-homie-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [Postman Collection](collections/span-rest-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/span-rest-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Website](https://www.span.io)
- [Portal](https://www.span.io)
- [Documentation](https://github.com/spanio/SPAN-API-Client-Docs)
- [Documentation](https://opensource.span.io/span-panel/)
- [Product](https://www.span.io/smart-panel-product)
- [Product](https://www.span.io/products/main-32)
- [Product](https://www.span.io/drive)
- [Product](https://www.span.io/app)
- [Product](https://www.span.io/utilities)
- [Blog](https://www.span.io/blog)
- [Announcement Post](https://www.span.io/blog/introducing-span-api-and-span-home-on-premise-public-beta)
- [Support](https://support.span.io/hc/en-us)
- [Terms of Service](https://www.span.io/terms-of-service)
- [Privacy Policy](https://www.span.io/privacy-policy)
- [GitHub Organization](https://github.com/spanio)
- [Repository](https://github.com/spanio/SPAN-API-Client-Docs)
- [Forum](https://github.com/spanio/SPAN-API-Client-Docs/discussions)
- [Issues](https://github.com/spanio/SPAN-API-Client-Docs/issues)
- [Changelog](https://github.com/spanio/SPAN-API-Client-Docs/blob/main/CHANGELOG.md)
- [License](https://github.com/spanio/SPAN-API-Client-Docs/blob/main/LICENSE)
- [SDK](https://github.com/SpanPanel/span-panel-api)
- [SDK](https://github.com/SpanPanel/Span)
- [SDK](https://github.com/SpanPanel/simulator)
- [Tool](https://github.com/spanio/SPAN-API-Client-Docs/tree/main/scripts)
- [Twitter](https://twitter.com/span_io)
- [LinkedIn](https://www.linkedin.com/company/span-io)
- [YouTube](https://www.youtube.com/@span_io)
- [Careers](https://www.span.io/careers)
- [Contact](https://www.span.io/contact)
- [Plans](plans/span-io-plans-pricing.yml)
- [Rate Limits](rate-limits/span-io-rate-limits.yml)
- [Fin Ops](finops/span-io-finops.yml)
- [Features](undefined)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
