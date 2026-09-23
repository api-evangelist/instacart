---
name: instacart-submit-catalog-data
description: >-
  Publish and maintain a retailer's catalog on Instacart — products that are the same across all
  stores, and store-level item attributes such as price and availability.
api: Instacart Catalog API
generated: '2026-08-27'
method: generated
source: >-
  openapi/instacart-products-api-openapi.yml, openapi/instacart-items-api-openapi.yml,
  openapi/_original/instacart-catalog-api-openapi.yml,
  https://docs.instacart.com/catalog/catalog_api/overview/,
  https://docs.instacart.com/connect/api/permissions_scopes
operations:
  - submitProducts
  - submitItems
---

# Submit catalog products and items

Partner-gated. Token: `client_credentials` with scope `connect:data_ingestion` (the value Instacart's
own Catalog API definition documents on its bearer scheme).

## The distinction that matters

- **Products** (`submitProducts`, `POST /v2/data_ingestion/catalog/product/submission`) are the same
  across every one of a retailer's stores: identity, brand, images, nutrition, variants.
- **Items** (`submitItems`, `POST /v2/data_ingestion/catalog/item/submission`) vary store by store:
  price, availability, in-store location, promotions, tax data, tare packaging, blackout periods.

Get this wrong and you will push a per-store price into a global record.

## Steps

1. **Meet the minimum catalog requirements** before anything else. Products missing required columns
   do not display on the storefront at all — they fail silently from the customer's point of view.
2. **Send UPC/GTIN.** Product identity across Instacart's matching, ads and Developer Platform surfaces
   is keyed on UPC. It is the one industry standard this API genuinely speaks.
3. **Submit products first, then items.** Item records attach store-level attributes to a product that
   must already exist.
4. **Handle the regulated columns deliberately.** SNAP EBT eligibility, California Prop 65 warnings,
   alcohol and cannabinoid requirements, and Quebec bilingual (en/fr) attribute content are all
   expressed as catalog fields. These are legal obligations encoded as data — do not let an agent
   populate them from inference.
5. **Availability is a field, not a delete.** Use `available`, the availability columns, or
   `blackout_times` to take something off the shelf for an interval. There is no unsubmit.

## Reversibility

None, in the undo sense. A catalog submission is corrected by submitting a new version of the record.
Plan a rollback as "re-submit the previous payload", and keep the previous payload.

## Errors

Standard Instacart envelope. Code `9999` with a populated `errors[]` array is the normal shape for a
bulk submission — expect several `meta.key` paths at once and fix them as a batch.
