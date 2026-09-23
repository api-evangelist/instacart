---
name: instacart-track-order-post-checkout
description: >-
  Drive an order-status experience after checkout — read order state and items, handle shopper
  replacement suggestions, and exchange chat messages with the shopper.
api: Instacart Connect Post-checkout API
generated: '2026-08-27'
method: generated
source: >-
  openapi/instacart-orders-api-openapi.yml, openapi/instacart-replacements-api-openapi.yml,
  openapi/instacart-chat-api-openapi.yml,
  openapi/_original/instacart-connect-post-checkout-api-openapi.yml,
  https://docs.instacart.com/connect/post-checkout,
  https://docs.instacart.com/connect/api/permissions_scopes
operations:
  - getOrder
  - getOrderItems
  - getOrderHandling
  - updateItemReplacement
  - getChatMessages
  - sendChatMessage
---

# Track an order after checkout

Partner-gated, and the token differs from the fulfillment flow: Post-checkout uses scope
`connect:post_checkout` with grant type `fulfillment_user_assertion` — a *user* token, not a client
token, because these calls act on one customer's order.

## Read the order

- `getOrder` — workflow state, time slot, store, delivery details.
- `getOrderItems` — the line items and their per-item status as the shopper works the aisles.
- `getOrderHandling` — handling details for the order.

Instacart's own tutorials describe a polling strategy for this while shopping is in progress. There is
no documented pagination on these collections; they come back whole.

## Handle replacements

When a shopper cannot find an item they suggest a replacement. `updateItemReplacement` records the
customer's decision — approve the suggestion, or ask for a refund.

Treat this as a one-way door. There is no published un-approve operation; once the decision is
submitted the correction path is Instacart's refund flow, not an endpoint. An agent should surface the
suggested replacement to the human and let them choose, rather than deciding on their behalf.

## Chat with the shopper

- `getChatMessages` — poll for messages from the shopper.
- `sendChatMessage` — send the customer's reply, and mark messages read.

## Timing

The whole surface is polling-based, but the underlying state changes are also published as event
callbacks on the fulfillment side (`picking`, `item found`, `item replaced`, `item refunded`,
`checkout`, `delivering`, `late delivery`, `customer missing`). If you already receive callbacks,
poll less and react to those instead. Callbacks may be redelivered.

## Errors

Standard Instacart envelope; `401` on this API usually means the user assertion has expired rather
than that the client credentials are wrong. Tokens live 24 hours.
