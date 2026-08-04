# Subbly (subbly)

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

Subbly is a subscription-first commerce platform for building and running subscription boxes, memberships, and recurring-product businesses without code. Beyond its no-code storefront and merchant admin, Subbly ships a developer surface for headless and custom builds.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/subbly/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/subbly/refs/heads/main/apis.yml)

## Access Model (read this first)

Subbly has a **real but only partially open** developer surface. What is documented and what is not:

- **SubblyCart.js** — a client-side embeddable cart widget, loaded from `https://assets.subbly.co/cart/cart-widget.js` and configured with a public `apiKey` from the Subbly admin (Shop Settings). Fully documented at [docs.subbly.dev/reference/cart](https://docs.subbly.dev/reference/cart/).
- **Subbly.js SDK** (`@subbly/sdk`) — a browser-side JavaScript client that calls Subbly's REST backend to manage products, bundles, carts, checkout/purchase, customers (auth, profiles, addresses, wallet), and subscriptions. Documented at [docs.subbly.dev/reference/subbly-sdk](https://docs.subbly.dev/reference/subbly-sdk/). **The SDK abstracts the underlying REST calls — Subbly does not publish concrete endpoint paths, a base API host, or an OpenAPI definition.**
- **Orders API (3PL)** — a real public Orders API for integrating Subbly orders directly with any third-party logistics / fulfillment provider. **Subbly provides its documentation on request** rather than publishing it openly, so it is access-gated.
- **Webhooks** — an in-app webhook platform that notifies external/internal services of order and subscription events, configured in the Subbly admin. Subbly does not publish a formal event catalog or payload schema.

Because Subbly does not publish REST endpoint paths, the OpenAPI and collections in this repo are **modeled** from the documented SDK operations to give the catalog a workable shape. They are clearly flagged as modeled and are **not** an official Subbly REST contract. No endpoints are modeled for the access-gated Orders API or for webhooks.

There is **no documented public WebSocket API** — all of Subbly's surfaces are request/response HTTP.

## Tags

- Subscriptions
- Subscription Commerce
- Ecommerce
- Subscription Box
- Recurring Billing
- Headless Commerce
- SDK
- Webhooks

## Timestamps

- **Created:** 2026-07-10
- **Modified:** 2026-07-10

## APIs

### Subbly Products API

List storefront products, load product variants and parent products, and work with bundles (load bundles, retrieve bundle items, generate bundle quotes). Surfaced through the Subbly.js SDK; endpoints modeled.

- **Human URL:** [https://docs.subbly.dev/reference/subbly-sdk/](https://docs.subbly.dev/reference/subbly-sdk/)

### Subbly Subscriptions API

Load and update a customer's subscriptions, including bundle selections and survey / preference management. Surfaced through the Subbly.js SDK; endpoints modeled.

- **Human URL:** [https://docs.subbly.dev/reference/subbly-sdk/](https://docs.subbly.dev/reference/subbly-sdk/)

### Subbly Customers API

Register and authenticate customers (password, OTP, social login, email verification), retrieve and update profiles, manage saved addresses, and manage stored payment methods / wallet. Surfaced through the Subbly.js SDK; endpoints modeled.

- **Human URL:** [https://docs.subbly.dev/reference/subbly-sdk/](https://docs.subbly.dev/reference/subbly-sdk/)

### Subbly Cart and Checkout API

Create and update carts, add/update/remove items, apply coupons and gift cards, set shipping methods and gifting dates, process checkout and purchase, and handle payment intents with 3DS verification. Client-side SubblyCart.js and the Subbly.js SDK are documented; server-side endpoints modeled.

- **Human URL:** [https://docs.subbly.dev/reference/cart/](https://docs.subbly.dev/reference/cart/)

### Subbly Orders API

Public Orders API for integrating Subbly orders directly with any 3PL / fulfillment provider. Documentation provided by Subbly on request — access-gated, no endpoints modeled.

- **Human URL:** [https://www.subbly.dev/](https://www.subbly.dev/)

### Subbly Webhooks

In-app webhook platform notifying external/internal services of order and subscription events with configurable conditions and variables. Configured in the Subbly admin; no published event schema.

- **Human URL:** [https://www.subbly.co/product](https://www.subbly.co/product)

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/subbly)
- [Website](https://www.subbly.co/)
- [Documentation](https://docs.subbly.dev/)
- [Developer Portal](https://www.subbly.dev/)
- [SDK](https://docs.subbly.dev/reference/subbly-sdk/)
- [Pricing](https://www.subbly.co/pricing)
- [Plans](plans/subbly-plans-pricing.yml)
- [Rate Limits](rate-limits/subbly-rate-limits.yml)
- [Fin Ops](finops/subbly-finops.yml)
- [Support / Help Center](https://support.subbly.co/)

## Pricing (as of 2026-07-10)

Subbly bills a monthly platform fee per plan tier plus a Subbly transaction fee (a percentage of each transaction), on top of the payment processor's own fees. Developer access is bundled with the plan.

| Plan | Monthly | Annual (effective/mo) | Subbly txn fee (Stripe) | Subbly txn fee (PayPal/Braintree) |
|------|---------|-----------------------|-------------------------|-----------------------------------|
| Lite | $19 | ~$14.25 ($171/yr) | 2% | 2.25% |
| Basic | $39 | ~$29.25 ($351/yr) | 1% | 1.25% |
| Subbly | $79 | ~$59.25 ($711/yr) | 1% | 1.25% |
| Advanced | $159 | ~$119.25 ($1,431/yr) | 1% | 1% |
| Subbly X (Enterprise) | from $499 | custom | 0.25–1% | 0.25–1% |

Some tiers also carry a small fixed per-transaction component (e.g. +$0.19 on Lite, +$0.15 on higher tiers) per the pricing page. Verify current numbers at [subbly.co/pricing](https://www.subbly.co/pricing).

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
