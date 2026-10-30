# Ibotta

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

Ibotta is a Denver-based consumer technology company (NYSE: IBTA) that operates a cash-back rewards platform and the Ibotta Performance Network (IPN), a digital promotions and retail-media network. Consumers earn real cash back on everyday purchases in-store and online through the Ibotta mobile app, browser extension, and connected retailer loyalty accounts. For brands, agencies, and retailers, the Ibotta Performance Network distributes digital rebates and promotions to more than 200 million shoppers across Ibotta's owned properties and a network of partner retailers and publishers (including Walmart, Dollar General, Family Dollar, and others). Ibotta was surfaced in the API Evangelist network as a portfolio company of GGV Capital. Ibotta publishes exactly one machine-readable API contract: the Ibotta Product API (an OpenAPI 3.0.1 document at ibotta.com/bex-api/api-docs.json), declared by the ChatGPT plugin manifest Ibotta still serves at ibotta.com/.well-known/ai-plugin.json — a single product-search operation backing the Ibotta browser extension, gated by a service bearer token that is not self-serve. The Ibotta Performance Network APIs that partners actually integrate against are documented only inside the IPN partner portal (portal.ipn.ibotta.com), which is behind Auth0 and reached through a sales conversation; no public IPN API reference, pricing, or rate-limit documentation exists.

**Areas:** Company · Consumer · Cashback · Rewards · Retail Media · Coupons · Loyalty · Shopping · Advertising · Promotions · Product Search · Retail

## Ibotta on APIs.io

Everything profiled for Ibotta is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/ibotta/](https://apis.io/providers/ibotta/)** — or go straight to one of the APIs or properties below.

### APIs (1)

- [Ibotta Openai API](https://apis.io/apis/ibotta/ibotta-openai-api/) — The Openai API from Ibotta — 1 operation(s) for openai.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [ibotta-mcp.yml](https://apis.io/servers/ibotta/ibotta-mcp-yml/)

#### Collections (1)

Postman and Open Collection request collections.

- [Ibotta Product API](https://apis.io/collections/ibotta/open-ibotta-product-api/)

#### Overlays (1)

OpenAPI overlays, including conversational phrasing for each operation.

- [Ibotta Product Api Overlay](https://apis.io/overlays/ibotta/ibotta-product-api-overlay/)

#### Security (3)

Authentication, trust centre, and vulnerability disclosure.

- [Ibotta Authentication](https://apis.io/security/ibotta/ibotta-authentication/)
- [Ibotta Domain Security](https://apis.io/security/ibotta/ibotta-domain-security/)
- [Ibotta Vulnerability Disclosure](https://apis.io/security/ibotta/ibotta-vulnerability-disclosure/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Ibotta Scopes](https://apis.io/scopes/ibotta/ibotta-scopes/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Ibotta Plans Pricing](https://apis.io/plans/ibotta/ibotta-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Ibotta Rate Limits](https://apis.io/rate-limits/ibotta/ibotta-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://home.ibotta.com/)
- [Documentation](https://ipn.ibotta.com/integrating-with-the-ipn)
- [Getting started](https://ipn.ibotta.com/resource-hub/ipn-integration)
- [Support](https://help.ibotta.com/)
- [Blog](https://home.ibotta.com/blog/)
- [Terms of service](https://legal.ibotta.com/)
- [Privacy policy](https://legal.ibotta.com/)
- [GitHub](https://github.com/Ibotta)

## API Evangelist rating

**Kin Score 32.1** — thin · rubric 0.24.0 · scored 2026-10-17

| Facet | Score |
|---|---|
| Discoverability | 66.1 |
| Contract quality | 43.5 |
| Contract governance | 4.5 |
| Operational transparency | 13.2 |
| Developer ergonomics | 42.3 |
| Access clarity | 6.6 |

**Agent readiness 32.2** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | — |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | served (partial credit) |
| Idempotency | — |
| Error Semantics | derived (partial credit) |
| OpenAPI Examples | — |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | — |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | served (partial credit) |
| Protected Resource Metadata | — |
| Dynamic Client Registration | yes |
| Agentic Commerce | — |

**Regulatory alignment 32.4** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/ibotta/](https://apis.io/providers/ibotta/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Ibotta: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/ibotta/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
