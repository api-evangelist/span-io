# SPAN (span-io)

SPAN is a San Francisco-based home energy technology company that builds smart electrical panels which replace traditional residential breaker boxes with a software-defined, controllable, and metered panel. SPAN Panel provides whole-home and per-circuit power/energy metering, remote relay control, whole-home backup coordination with solar and energy storage, and EV charging integration via SPAN Drive. As of the SPAN Panel firmware r202603 release (Q1 2026), SPAN exposes a public-beta on-premise SPAN API for software integrations between SPAN Panel and other devices on the home LAN.

**URL:** [Visit APIs.json](https://raw.githubusercontent.com/api-evangelist/span-io/refs/heads/main/apis.yml)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=company-api-evangelist&utm_content=repo)

## Tags

 - Energy, Home Energy, Electrification, Smart Panel, Electrical Panel, Home Automation, Solar, Energy Storage, EV Charging, Grid, Islanding, Backup Power, Demand Response, IoT, MQTT, Homie, Electrification Bus, On-Premise

## Timestamps

- **Created:** 2026-05-25
- **Modified:** 2026-05-25

## APIs

### SPAN REST API

Local on-premise HTTP/JSON REST API hosted directly on SPAN Panel. Authentication is HTTP Bearer JWT minted by the panel via `POST /api/v1/auth/register` and bound to a named API client. The surface exposes system status, Wi-Fi scan/connect, panel state, main meter, panel power, islanding state, per-circuit control, panel grid relay, emergency reconnect, and energy storage state-of-energy and nice-to-have thresholds.

**Human URL:** [https://github.com/spanio/SPAN-API-Client-Docs](https://github.com/spanio/SPAN-API-Client-Docs)

**Base URL:** `http://span-{serial-number}.local/api/v1`

- [OpenAPI](openapi/span-rest-api-openapi.json)
- [Documentation — SPAN-API-Client-Docs](https://github.com/spanio/SPAN-API-Client-Docs)
- [Documentation — Public Beta announcement](https://www.span.io/blog/introducing-span-api-and-span-home-on-premise-public-beta)
- [JSON Schema — mDNS Services](json-schema/span-mdns-services-schema.json)
- [JSON-LD Context](json-ld/span-context.jsonld)
- [Naftiko Capability — Circuits](capabilities/circuits.yaml)
- [Naftiko Capability — Panel](capabilities/panel.yaml)
- [Naftiko Capability — Storage](capabilities/storage.yaml)
- [Naftiko Capability — Auth](capabilities/auth.yaml)
- [Naftiko Capability — Wi-Fi](capabilities/wifi.yaml)

### SPAN eBus MQTT API

Publish/subscribe streaming API hosted on SPAN Panel using the Electrification Bus (eBus) framework and the Homie Convention. SPAN Panel hosts an MQTT broker available over MQTTS (port 8883), WS, and WSS. Clients subscribe to `ebus/5/<serial>/...` topics for real-time panel state, per-circuit telemetry, energy storage state, and SPAN Drive integration data; clients publish to Homie `/set` topics to operate relays. Broker ACLs grant full read on `ebus/#`, write access only to `/set` and to non-panel device subtrees.

**Human URL:** [https://github.com/spanio/SPAN-API-Client-Docs#span-api-interaction-models](https://github.com/spanio/SPAN-API-Client-Docs#span-api-interaction-models)

- [AsyncAPI](asyncapi/span-ebus-asyncapi.yml)
- [JSON Schema — Homie Device Description](json-schema/span-homie-schema.json)
- [Naftiko Capability — eBus Telemetry](capabilities/ebus-telemetry.yaml)

## Common Properties

- [Portal — span.io](https://www.span.io)
- [Documentation — SPAN-API-Client-Docs](https://github.com/spanio/SPAN-API-Client-Docs)
- [Documentation — opensource.span.io](https://opensource.span.io/span-panel/)
- [AnnouncementPost — Introducing SPAN API and SPAN Home On-premise](https://www.span.io/blog/introducing-span-api-and-span-home-on-premise-public-beta)
- [Product — SPAN Panel](https://www.span.io/smart-panel-product)
- [Product — SPAN Panel MAIN 32](https://www.span.io/products/main-32)
- [Product — SPAN Drive](https://www.span.io/drive)
- [Product — SPAN Home App](https://www.span.io/app)
- [Product — SPAN Utilities (DERMS)](https://www.span.io/utilities)
- [GitHubOrganization — spanio](https://github.com/spanio)
- [Repository — SPAN-API-Client-Docs](https://github.com/spanio/SPAN-API-Client-Docs)
- [Forum — GitHub Discussions](https://github.com/spanio/SPAN-API-Client-Docs/discussions)
- [Issues — GitHub Issues](https://github.com/spanio/SPAN-API-Client-Docs/issues)
- [ChangeLog](https://github.com/spanio/SPAN-API-Client-Docs/blob/main/CHANGELOG.md)
- [License — MIT-0 (docs and example code)](https://github.com/spanio/SPAN-API-Client-Docs/blob/main/LICENSE)
- [Support — support.span.io](https://support.span.io/hc/en-us)
- [TermsOfService](https://www.span.io/terms-of-service)
- [PrivacyPolicy](https://www.span.io/privacy-policy)
- [SDK — span-panel-api (Python, community)](https://github.com/SpanPanel/span-panel-api)
- [SDK — Home Assistant Integration (community)](https://github.com/SpanPanel/Span)
- [SDK — SPAN Panel eBus Simulator (community)](https://github.com/SpanPanel/simulator)
- [Tool — Reference scripts](https://github.com/spanio/SPAN-API-Client-Docs/tree/main/scripts)
- [Twitter](https://twitter.com/span_io)
- [LinkedIn](https://www.linkedin.com/company/span-io)
- [YouTube](https://www.youtube.com/@span_io)

## Artifacts

### OpenAPI

- [SPAN REST API](openapi/span-rest-api-openapi.json)

### AsyncAPI

- [SPAN eBus MQTT API](asyncapi/span-ebus-asyncapi.yml)

### JSON Schema

- [Homie Device Description Schema](json-schema/span-homie-schema.json)
- [mDNS Services Schema](json-schema/span-mdns-services-schema.json)

### JSON-LD

- [SPAN Context](json-ld/span-context.jsonld)

### Capabilities (Naftiko)

- [Auth](capabilities/auth.yaml)
- [Wi-Fi](capabilities/wifi.yaml)
- [Panel](capabilities/panel.yaml)
- [Circuits](capabilities/circuits.yaml)
- [Storage](capabilities/storage.yaml)
- [eBus Telemetry](capabilities/ebus-telemetry.yaml)

### Spectral Rules

- [SPAN API Rules](rules/span-io-rules.yml)

### Vocabulary

- [SPAN Vocabulary](vocabulary/span-io-vocabulary.yml)

### Commercial Artifacts

- [Plans / Pricing](plans/span-io-plans-pricing.yml)
- [Rate Limits](rate-limits/span-io-rate-limits.yml)
- [FinOps Definition](finops/span-io-finops.yml)

## Maintainers

**FN:** Kin Lane

**Email:** kin@apievangelist.com
