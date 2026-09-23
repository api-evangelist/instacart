---
name: instacart-place-delivery-order
description: >-
  Run the Instacart Connect fulfillment flow end to end — find a store, preview and reserve a time
  slot, create the delivery order, and cancel it while the cancel window is still open.
api: Instacart Connect Fulfillment API
generated: '2026-08-27'
method: generated
source: >-
  openapi/instacart-delivery-api-openapi.yml,
  openapi/_original/instacart-connect-fulfillment-api-openapi.yml,
  https://docs.instacart.com/connect/api/fulfillment/overview,
  https://docs.instacart.com/connect/api/fulfillment/delivery/cancel_order,
  https://docs.instacart.com/connect/api/permissions_scopes
operations:
  - generateAccessToken
  - findDeliveryStores
  - previewDeliveryTimeSlots
  - reserveDeliveryTimeSlot
  - createDeliveryOrder
  - getOrder
  - cancelOrder
---

# Place and manage an Instacart Connect delivery order

Partner-gated. You need a client ID and secret issued by Instacart before any of this works.

## 1. Get a token

`POST https://connect.instacart.com/v2/oauth/token` (`generateAccessToken`) with
`grant_type=client_credentials` and `scope=connect:fulfillment`.

Two rules that bite: send `client_id` and `client_secret` **in the request body** — passing them as
query parameters returns `403` — and reuse the token, because it is valid for 24 hours.

## 2. Find a store

`findDeliveryStores` returns the stores that can fulfil to the customer's location. No store, no order.

## 3. Preview, then reserve, a time slot

`previewDeliveryTimeSlots` shows what is available; `reserveDeliveryTimeSlot` holds one. Reserve before
you create — the older "reserve a previewed time slot with cart" endpoint is deprecated in favour of
the plain reserve endpoint.

## 4. Create the order

`createDeliveryOrder`. `user_id` is *yours*: any unique identifier you control — a login name, a
loyalty ID, an email address. It is the one join key in this API you own, so pick a scheme and keep it
stable.

There is no idempotency key. If the call times out, do **not** blind-retry — poll `getOrder` first, or
you will create a duplicate order for a real household.

## 5. Know your cancel window before you commit

`cancelOrder` — `POST /v2/fulfillment/users/{user_id}/orders/{order_id}/cancel` — works **only while
the order status is `brand_new`**. The moment a shopper is assigned and the status moves to
`acknowledged`, this endpoint can no longer cancel the order. That is the entire reversibility budget
for this flow, and it is measured in shopper-assignment latency, not in minutes you control.

Practical consequence for an agent: if you are not certain of the order, do not place it. Confirm with
the human first. Once `acknowledged` lands, unwinding is a support conversation, not an API call.

## 6. Watch it happen

`getOrder` polls status. Better: configure event callbacks
(`/connect/api/fulfillment/communications/event_callbacks`) and receive `brand_new`, `acknowledged`,
`picking`, `checkout`, `delivering` and the item-level events as they occur. Callbacks are
at-least-once — Instacart states the same event can arrive more than once when an order reverts to a
previous status — so your receiver must be idempotent even though the API is not.

## Errors

`{"error":{"message":…,"code":…},"meta":{"key":…}}`. Code `9999` means the `errors[]` array holds
several failures at once, each with its own `meta.key`. See `errors/instacart-problem-types.yml`.

## Rehearse first

The Connect Sandbox API will drive this whole state machine for you without a real shopper: generate a
batch, advance its status, create a shopper, have that shopper find, replace and refund items, and fire
callbacks at your endpoint. See `sandbox/instacart-sandbox.yml`.
