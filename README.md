# Instacart

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

Instacart (Maplebear Inc.) is a North American grocery technology company that operates the Instacart Marketplace and sells its underlying commerce, fulfillment, catalog, advertising and storefront technology to retailers and brands. Its published API surface splits cleanly in two. The Instacart Developer Platform API is open to app and website developers, costs nothing, and exposes two shoppable-page operations plus a nearby-retailers lookup at connect.instacart.com/idp/v1 -- and, unusually, Instacart pays the developer, commissioning attributed orders through an Impact affiliate programme. Instacart Connect is the enterprise half: OAuth 2.0, partner-gated Fulfillment, Post-checkout, Transaction and Sandbox APIs, the Catalog API, Carrot Ads and Shopping Widgets, all bundled into a retailer or brand partner agreement. Instacart also runs a first-party remote Model Context Protocol server at https://mcp.instacart.com/mcp whose tools/list is served anonymously, making it one of the few grocery-sector providers with a directly reachable agent surface.

**Areas:** Grocery · E-Commerce · Marketplace · Retail · Logistics · Last Mile Delivery · Fulfillment · Catalog · Advertising · Agents · MCP · Agentic Commerce

## Instacart on APIs.io

Everything profiled for Instacart is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/instacart/](https://apis.io/providers/instacart/)** — or go straight to one of the APIs or properties below.

### APIs (12)

- [Instacart Shopping Widgets](https://apis.io/apis/instacart/shopping-widgets/) — Instacart Shopping Widgets are front-end web components that retailers can embed into their websites to add e-commerce functionalities powered by Instacart…
- [instacart Authentication API](https://apis.io/apis/instacart/instacart-authentication-api/) — Endpoints for obtaining and managing OAuth 2.0 access tokens used to authenticate API requests.
- [instacart Chat API](https://apis.io/apis/instacart/instacart-chat-api/) — Endpoints for shopper-customer communication including sending and retrieving chat messages.
- [instacart Delivery API](https://apis.io/apis/instacart/instacart-delivery-api/) — Endpoints for finding delivery stores, previewing time slots, reserving time slots, and creating delivery orders.
- [instacart Items API](https://apis.io/apis/instacart/instacart-items-api/) — Endpoints for updating item-level attributes such as pricing and availability at specific store locations. Items contain information that can vary from one…
- [instacart Last Mile Delivery API](https://apis.io/apis/instacart/instacart-last-mile-delivery-api/) — Endpoints for last mile delivery where items are pre-packed and only require delivery from the store to the customer.
- [instacart Orders API](https://apis.io/apis/instacart/instacart-orders-api/) — Endpoints for retrieving order status, handling details, and item information after checkout.
- [instacart Pickup API](https://apis.io/apis/instacart/instacart-pickup-api/) — Endpoints for finding pickup stores, previewing time slots, reserving time slots, and creating pickup orders.
- [instacart Products API](https://apis.io/apis/instacart/instacart-products-api/) — Endpoints for creating and updating products in the retailer's catalog on Instacart. Products are the same across all of a retailer's stores.
- [instacart Replacements API](https://apis.io/apis/instacart/instacart-replacements-api/) — Endpoints for managing item replacements suggested by shoppers during order fulfillment.
- [Instacart Developer Platform MCP Server](https://apis.io/apis/instacart/instacart-mcp-server/) — Instacart's first-party remote Model Context Protocol server. Production endpoint https://mcp.instacart.com/mcp over Streamable HTTP, authenticated with a…
- [instacart Rest API](https://apis.io/apis/instacart/instacart-rest-api/) — The Rest API from instacart — 1 operation(s) for rest.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Instacart Connect Event Callbacks](https://apis.io/asyncapis/instacart/instacart-connect-events-asyncapi/)

#### Event channels (1)

Individual events and webhooks the provider emits.

- [/webhook](https://apis.io/channels/instacart/webhook/)

#### GraphQL (1)

GraphQL schemas.

- [Moved to /providers/instacart/](https://apis.io/graphqls/instacart/instacart-graphql/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [Instacart Developer Platform MCP Server](https://apis.io/servers/instacart/instacart-developer-platform-mcp-server/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Instacart Agentic Access](https://apis.io/agentic-access/instacart/instacart-agentic-access/)

#### JSON Schema (35)

The data models the API reads and writes.

- [CartItem](https://apis.io/schemas/instacart/instacart-cartitem/)
- [ChatMessage](https://apis.io/schemas/instacart/instacart-chatmessage/)
- [ChatMessagesResponse](https://apis.io/schemas/instacart/instacart-chatmessagesresponse/)
- [CreateOrderRequest](https://apis.io/schemas/instacart/instacart-createorderrequest/)
- [Error](https://apis.io/schemas/instacart/instacart-error/)
- [FindStoresRequest](https://apis.io/schemas/instacart/instacart-findstoresrequest/)
- [Ingredient](https://apis.io/schemas/instacart/instacart-ingredient/)
- [Item](https://apis.io/schemas/instacart/instacart-item/)
- [ItemSubmissionRequest](https://apis.io/schemas/instacart/instacart-itemsubmissionrequest/)
- [LineItem](https://apis.io/schemas/instacart/instacart-lineitem/)
- [Instacart Order](https://apis.io/schemas/instacart/instacart-order/)
- [OrderHandlingResponse](https://apis.io/schemas/instacart/instacart-orderhandlingresponse/)
- [OrderItem](https://apis.io/schemas/instacart/instacart-orderitem/)
- [OrderItemsResponse](https://apis.io/schemas/instacart/instacart-orderitemsresponse/)
- [OrderResponse](https://apis.io/schemas/instacart/instacart-orderresponse/)
- [PostCheckoutOrderItem](https://apis.io/schemas/instacart/instacart-postcheckoutorderitem/)
- [PreviewServiceOptionsRequest](https://apis.io/schemas/instacart/instacart-previewserviceoptionsrequest/)
- [Instacart Product](https://apis.io/schemas/instacart/instacart-product/)
- [ProductsLinkResponse](https://apis.io/schemas/instacart/instacart-productslinkresponse/)
- [ProductSubmissionRequest](https://apis.io/schemas/instacart/instacart-productsubmissionrequest/)
- [RecipeRequest](https://apis.io/schemas/instacart/instacart-reciperequest/)
- [Replacement](https://apis.io/schemas/instacart/instacart-replacement/)
- [ReplacementDecisionRequest](https://apis.io/schemas/instacart/instacart-replacementdecisionrequest/)
- [ReplacementResponse](https://apis.io/schemas/instacart/instacart-replacementresponse/)
- [ReserveTimeSlotRequest](https://apis.io/schemas/instacart/instacart-reservetimeslotrequest/)
- …and 10 more published on APIs.io

#### JSON Structure (1)

Data models expressed in JSON Structure.

- [Instacart Structure](https://apis.io/json-structure/instacart/instacart-structure/)

#### JSON-LD (1)

Linked-data contexts for the provider's vocabulary.

- [Instacart Context](https://apis.io/jsonld/instacart/instacart-context/)

#### Vocabulary (1)

The provider's domain terms, defined.

- [Instacart Domain Vocabulary](https://apis.io/vocabularies/instacart/instacart-vocabulary/)

#### Collections (13)

Postman and Open Collection request collections.

- [Instacart Catalog Authentication API](https://apis.io/collections/instacart/open-instacart-authentication-api/)
- [Instacart Catalog API](https://apis.io/collections/instacart/open-instacart-catalog-api/)
- [Instacart Catalog Authentication Chat API](https://apis.io/collections/instacart/open-instacart-chat-api/)
- [Instacart Connect Fulfillment API](https://apis.io/collections/instacart/open-instacart-connect-fulfillment-api/)
- [Instacart Connect Post-Checkout API](https://apis.io/collections/instacart/open-instacart-connect-post-checkout-api/)
- [Instacart Catalog Authentication Delivery API](https://apis.io/collections/instacart/open-instacart-delivery-api/)
- [Instacart Developer Platform API](https://apis.io/collections/instacart/open-instacart-developer-platform-api/)
- [Instacart Catalog Authentication Items API](https://apis.io/collections/instacart/open-instacart-items-api/)
- [Instacart Catalog Authentication Last Mile Delivery API](https://apis.io/collections/instacart/open-instacart-last-mile-delivery-api/)
- [Instacart Catalog Authentication Orders API](https://apis.io/collections/instacart/open-instacart-orders-api/)
- [Instacart Catalog Authentication Pickup API](https://apis.io/collections/instacart/open-instacart-pickup-api/)
- [Instacart Catalog Authentication Products API](https://apis.io/collections/instacart/open-instacart-products-api/)
- [Instacart Catalog Authentication Replacements API](https://apis.io/collections/instacart/open-instacart-replacements-api/)

#### Overlays (20)

OpenAPI overlays, including conversational phrasing for each operation.

- [Instacart Authentication Api Overlay](https://apis.io/overlays/instacart/instacart-authentication-api-overlay/)
- [Instacart Authentication Api Phrasing Overlay](https://apis.io/overlays/instacart/instacart-authentication-api-phrasing-overlay/)
- [Instacart Chat Api Overlay](https://apis.io/overlays/instacart/instacart-chat-api-overlay/)
- [Instacart Chat Api Phrasing Overlay](https://apis.io/overlays/instacart/instacart-chat-api-phrasing-overlay/)
- [Instacart Delivery Api Overlay](https://apis.io/overlays/instacart/instacart-delivery-api-overlay/)
- [Instacart Delivery Api Phrasing Overlay](https://apis.io/overlays/instacart/instacart-delivery-api-phrasing-overlay/)
- [Instacart Items Api Overlay](https://apis.io/overlays/instacart/instacart-items-api-overlay/)
- [Instacart Items Api Phrasing Overlay](https://apis.io/overlays/instacart/instacart-items-api-phrasing-overlay/)
- [Instacart Last Mile Delivery Api Overlay](https://apis.io/overlays/instacart/instacart-last-mile-delivery-api-overlay/)
- [Instacart Last Mile Delivery Api Phrasing Overlay](https://apis.io/overlays/instacart/instacart-last-mile-delivery-api-phrasing-overlay/)
- [Instacart Llm Integration Overlay](https://apis.io/overlays/instacart/instacart-llm-integration-overlay/)
- [Instacart Orders Api Overlay](https://apis.io/overlays/instacart/instacart-orders-api-overlay/)
- [Instacart Orders Api Phrasing Overlay](https://apis.io/overlays/instacart/instacart-orders-api-phrasing-overlay/)
- [Instacart Pickup Api Overlay](https://apis.io/overlays/instacart/instacart-pickup-api-overlay/)
- [Instacart Pickup Api Phrasing Overlay](https://apis.io/overlays/instacart/instacart-pickup-api-phrasing-overlay/)
- [Instacart Products Api Overlay](https://apis.io/overlays/instacart/instacart-products-api-overlay/)
- [Instacart Products Api Phrasing Overlay](https://apis.io/overlays/instacart/instacart-products-api-phrasing-overlay/)
- [Instacart Replacements Api Overlay](https://apis.io/overlays/instacart/instacart-replacements-api-overlay/)
- [Instacart Replacements Api Phrasing Overlay](https://apis.io/overlays/instacart/instacart-replacements-api-phrasing-overlay/)
- [Instacart Rest Api Phrasing Overlay](https://apis.io/overlays/instacart/instacart-rest-api-phrasing-overlay/)

#### Governance rules (2)

Spectral rulesets for the provider's contracts.

- [Instacart — asyncapi rules](https://apis.io/rules/instacart/instacart-asyncapi-spectral-rules/)
- [Instacart — jsonschema rules](https://apis.io/rules/instacart/instacart-jsonschema-spectral-rules/)

#### Security (3)

Authentication, trust centre, and vulnerability disclosure.

- [Instacart Authentication](https://apis.io/security/instacart/instacart-authentication/)
- [Instacart Domain Security](https://apis.io/security/instacart/instacart-domain-security/)
- [Instacart Vulnerability Disclosure](https://apis.io/security/instacart/instacart-vulnerability-disclosure/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Instacart Scopes](https://apis.io/scopes/instacart/instacart-scopes/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Instacart Plans Pricing](https://apis.io/plans/instacart/instacart-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Instacart Rate Limits](https://apis.io/rate-limits/instacart/instacart-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Instacart Finops](https://apis.io/finops/instacart/instacart-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.instacart.com/)
- [Documentation](https://docs.instacart.com/)
- [Getting started](https://docs.instacart.com/developer_platform_api/get_started/overview)
- [API reference](https://docs.instacart.com/developer_platform_api/api/overview)
- [Support](https://instacart.atlassian.net/servicedesk/customer/portal/1)
- [Changelog](https://docs.instacart.com/developer_platform_api/api/changelog)
- [Blog](https://company.instacart.com/blog)
- [Security](https://hackerone.com/instacart)
- [Terms of service](https://www.instacart.com/terms)
- [Privacy policy](https://www.instacart.com/privacy)
- [GitHub](https://github.com/instacart)
- [Status](https://enterprise-status.instacart.com/)

## API Evangelist rating

**Kin Score 70.0** — exemplar · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 80.0 |
| Contract quality | 63.6 |
| Contract governance | 31.8 |
| Operational transparency | 81.6 |
| Developer ergonomics | 66.1 |
| Access clarity | 65.8 |

**Agent readiness 37.9** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | documented (partial credit) |
| MCP Server | verified |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | verified |
| OpenAPI Examples | — |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | derived (partial credit) |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | — |
| Operation Distinctiveness | distinct |

**Regulatory alignment 40.2** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/instacart/](https://apis.io/providers/instacart/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Instacart: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/instacart/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
