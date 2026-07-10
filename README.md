# Subbly (subbly)

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
