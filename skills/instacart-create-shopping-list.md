---
name: instacart-create-shopping-list
description: >-
  Build a shoppable Instacart shopping-list page from a set of grocery items and return a shareable
  link, with UPC-precise matching where product codes are known.
api: Instacart Developer Platform API
generated: '2026-08-27'
method: generated
source: >-
  openapi/_original/instacart-developer-platform-api-openapi.yml,
  mcp/instacart-mcp-tools.json (live tools/list 2026-08-27),
  https://docs.instacart.com/developer_platform_api/api/products/create_shopping_list_page,
  https://docs.instacart.com/developer_platform_api/api/changelog
operations:
  - createShoppingListPage
mcp_tools:
  - create-shopping-list
---

# Create a shopping list page

Creates a shopping list page on Instacart Marketplace and returns a shareable link. Customers open it,
pick a store, and check out.

## Two ways in

| Surface | Endpoint | Auth |
| --- | --- | --- |
| REST | `POST https://connect.instacart.com/idp/v1/products/products_link` (`createShoppingListPage`) | `Authorization: Bearer keys.…` |
| MCP | tool `create-shopping-list` at `https://mcp.instacart.com/mcp` | same API key as an `Authorization` Bearer header |

## Steps

1. **Assemble the line items.** `title` and at least one line item are required. Each line item needs
   a `name`; `displayText` controls what the shopper sees.
2. **Send UPCs when you have them.** The `upcs` array was added on 2025-09-18 and changes the matching
   behaviour outright: when UPCs are present, Instacart searches *exclusively* on those identifiers and
   prioritises retailers that carry a match. This is the single highest-leverage field in the contract.
3. **Use `line_item_measurements`, not `quantity`/`unit`.** Instacart deprecated the flat
   `quantity` and `unit` fields on `LineItem` on 2026-03-18 in favour of the `line_item_measurements`
   array, which lets a retailer supply several measurements per item so Instacart can pick the best one.
   Note the MCP `create-shopping-list` tool schema still exposes the old flat fields — the agent surface
   is one deprecation behind the REST surface, so prefer REST when measurements matter.
4. **Set an expiry if the list is time-bound.** `expires_in` is in days. Without it, the docs say the
   list never expires — and there is no delete operation, so an unexpiring list is permanent.
5. **Configure the landing page** if you want attribution: `landingPageConfiguration.partnerLinkbackUrl`
   sends customers back to you, and `enablePantryItems` stops pantry staples being auto-added.
6. **Cache the returned URL.** Instacart's own best-practice section says so, and there is no
   idempotency key — retrying a timed-out call creates a second list.

## What can go wrong

Same envelope as every Instacart API: `error.code` plus `meta.key`. `400`/`1001` names the bad field.
`429` is the per-second threshold with no header telling you how much budget remains.

## Reversibility

No delete. `expires_in` is the only lifetime control, and it must be set at creation time.
