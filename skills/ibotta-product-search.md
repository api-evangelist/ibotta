---
name: ibotta-product-search
description: >-
  Search Ibotta's browser-extension product coverage for products matching one or more keyword
  queries, optionally constrained to a price range or a single retailer, and read the returned
  price signals (hidden deals, price ranges, availability) correctly.
api: Ibotta Product API
base_url: https://api.ibops.net/bex-api
operations:
  - searchProducts
generated: '2026-08-12'
method: generated
source: >-
  Grounded in openapi/ibotta-product-api-openapi.yml (operationId searchProducts) plus
  conventions/ibotta-conventions.yml, errors/ibotta-problem-types.yml and
  authentication/ibotta-authentication.yml. Every operationId, field name and status code below
  appears in the published contract or was observed live.
---

# Search Ibotta products

The Ibotta Product API exposes exactly one operation. There is no store lookup, no offer
lookup, and no pagination — plan around that before you start.

## Before you call

Authentication is a **service-level bearer token**, not a per-user credential
(`has_user_authentication` is `false` in Ibotta's own plugin manifest). There is no published
key-issuance flow. If you do not already hold a token, this API is not callable — an anonymous
request returns `401 {"message":"Unauthorized"}`.

```
Authorization: Bearer <service token>
Content-Type: application/json
```

## Step 1 — build the query set

`searchProducts` is `POST /openai/search`. The body is `ProductSearchBody`:

| field      | type            | required | notes |
|------------|-----------------|----------|-------|
| `queries`  | array of string | yes      | at least one entry (`minItems: 1`) |
| `limit`    | number          | yes      | defaults to `25` |
| `minPrice` | number          | no       | defaults to `0` |
| `maxPrice` | number          | no       | nullable |
| `storeId`  | string          | no       | nullable; restricts results to one retailer |

Send several short, concrete product terms in `queries` rather than one long sentence — the
field is named "The search query for product names", so it matches against product names, not
against natural-language intent.

```json
{
  "queries": ["shampoo", "dry shampoo", "head and shoulders"],
  "limit": 25,
  "minPrice": 0,
  "maxPrice": 15
}
```

## Step 2 — call it and handle the failure modes

```
POST https://api.ibops.net/bex-api/openai/search
```

There is no `Idempotency-Key` and no request-id header; a retry is a fresh, uncorrelated
request. The operation is a read, so retrying is safe.

| status | body | what to do |
|--------|------|------------|
| `200`  | `{"products": [...]}` | proceed to step 3 |
| `401`  | `{"message":"Unauthorized"}` | token missing or invalid — do not retry |
| `403`  | `{"message": ...}` | the surface has been turned off by Ibotta; non-retryable, fall back to the Ibotta app or browser extension |

Errors are a flat `{"message": string}` — **not** RFC 9457 problem+json. There is no error code
and no correlation id, so you cannot branch on anything finer than the HTTP status. No `429` is
declared and no rate-limit headers are returned; if you are batching, throttle yourself.

## Step 3 — read the price fields correctly

Each entry in `products` is a `Product`. The `price` object has six required members, and two
of them are traps:

- `isHiddenDeal: true` means the shown `value` is **higher** than the real price — the retailer
  only reveals the true price in-cart. Do not present `value` as the price to a user in this
  case; say the real price is revealed at checkout.
- `isRange: true` means the product is priced as a band. `minPrice` and `maxPrice` differ, and
  `value` is still populated — decide explicitly which one you surface, and be consistent.
- `currency` is per-product; do not assume USD.

Also check `isAvailable` before recommending anything. `views` is a popularity signal, not a
ranking guarantee — the API does not document a sort order.

## Step 4 — identify and link products

- `productUrl` is the retailer's product page. Always link the product name to it.
- `uniqueIds.upc` is the only cross-retailer join key. `uniqueIds.sku` is meaningful **only**
  within the same `storeId`.
- `storeId` is an opaque string with no documented grammar, no enumeration, and no lookup
  operation. You cannot resolve it to a retailer name through this API. If you need a retailer
  label, `merchantInfo` is the only field carrying one — and it is unstructured free text.

## Limits you cannot work around

`limit` is a cap, not a page size. There is no `offset`, `cursor`, or `page` parameter and the
response carries no pagination metadata, so results beyond `limit` are unreachable. If you need
broader coverage, widen `queries` rather than trying to page.
