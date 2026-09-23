---
name: instacart-create-shoppable-recipe
description: >-
  Turn a recipe into a shoppable Instacart Marketplace page and return the link, either through the
  Developer Platform REST API or through Instacart's remote MCP server.
api: Instacart Developer Platform API
generated: '2026-08-27'
method: generated
source: >-
  openapi/_original/instacart-developer-platform-api-openapi.yml,
  mcp/instacart-mcp-tools.json (live tools/list 2026-08-27),
  https://docs.instacart.com/developer_platform_api/api/products/create_recipe_page
operations:
  - createRecipePage
mcp_tools:
  - create-recipe
---

# Create a shoppable recipe page

Creates a recipe page on Instacart Marketplace and returns a unique URL. When someone opens the
link they pick a store, the ingredients land in a cart, and they check out.

## Two ways in

| Surface | Endpoint | Auth |
| --- | --- | --- |
| REST | `POST https://connect.instacart.com/idp/v1/products/recipe` (`createRecipePage`) | `Authorization: Bearer keys.…` |
| MCP | tool `create-recipe` at `https://mcp.instacart.com/mcp` | same API key as an `Authorization` Bearer header |

Use the development host `https://connect.dev.instacart.tools` (or `https://mcp.dev.instacart.tools/mcp`)
with a development key until your integration passes Instacart's production-key review.

## Steps

1. **Collect the recipe.** `title` and at least one ingredient are the only required inputs. Optional:
   `image_url` (500x500), `author`, `servings`, `cooking_time` (minutes), `instructions[]`.
2. **Split compound ingredients.** "butter or margarine" must become two ingredients; "salt and pepper
   to taste" must become two. Instacart's own plugin manifest is emphatic about this — a bundled
   string matches nothing in a store catalogue.
3. **Keep the quantity with the ingredient.** Each ingredient takes `name` (required), `quantity`,
   `unit` and an optional `displayText`. Use the published units of measurement list rather than
   free-form units — see `/developer_platform_api/api/units_of_measurement`.
4. **Drop what the user already has.** If the person said they have the pasta, leave it out.
5. **Call the operation.** `Content-Type: application/json` is required, and so is HTTPS — plain HTTP
   requests fail.
6. **Return the URL.** Cache it. Each call generates a *new* page with a *new* URL: there is no
   idempotency key on this API, so a retry after a timeout creates a second page rather than
   returning the first.

## What can go wrong

Errors come back as `{"error":{"message":…,"code":…},"meta":{"key":…}}` — read `error.code` together
with `meta.key` to know which field is wrong. `1001` is an invalid parameter named by `meta.key`.
`401` means the key is wrong or missing; `429` means you exceeded the per-second threshold — back off
exponentially, because Instacart publishes no `RateLimit-*` headers and no `Retry-After`, so the
rejection is the only signal you get. `5xx` is retryable. See `errors/instacart-problem-types.yml`.

## Reversibility

There is none. A recipe page, once created, has no published delete or expiry operation. Confirm the
recipe with the user *before* calling, not after — see `conventions/instacart-conventions.yml`.
