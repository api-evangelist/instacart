# Instacart GraphQL Schema

## Overview

This conceptual GraphQL schema models the Instacart grocery delivery and retail platform. Instacart provides APIs for retailers, brands, and developers to integrate grocery shopping, delivery, fulfillment, and catalog management capabilities. The schema covers the full lifecycle of a grocery order — from browsing stores and products through checkout, delivery, and post-order tracking.

Instacart operates as a platform connecting consumers with retail stores through a network of shoppers who fulfill delivery and pickup orders. The platform supports multiple retailer integrations, brand advertising, and developer tooling.

## Schema Source

This is a conceptual schema derived from:

- Instacart Developer Platform API documentation: https://docs.instacart.com/developer_platform_api/
- Instacart Connect Fulfillment API: https://docs.instacart.com/connect/fulfillment/
- Instacart Connect Post-Checkout API: https://docs.instacart.com/connect/post-checkout/
- Instacart Catalog API: https://docs.instacart.com/catalog/catalog_api/overview/
- Instacart Shopping Widgets: https://docs.instacart.com/widgets/
- GitHub organization: https://github.com/instacart

## Domain Coverage

The schema covers the following functional domains:

**Retail Store Management** — Store locations, hours, departments, zones, and aisles. Retailers integrate their physical and digital store presence through the Connect APIs.

**Product Catalog** — Products, items, categories, brands, images, nutritional information, food labels, certifications, and pricing. The Catalog API enables retailers to manage their product listings programmatically.

**Pricing and Promotions** — Regular pricing, sale pricing, unit pricing, per-weight pricing, coupons, and sale events. Brand promotions and brand pages support advertising integrations.

**Inventory and Availability** — Stock levels, item availability, substitutions, and substitution preferences. Shoppers use this data when fulfilling orders.

**Fulfillment** — Delivery windows, pickup windows, fulfillment options, order fulfillment tracking, delivery drivers, driver location, and delivery proof.

**Shopping and Orders** — Carts, cart items, cart summaries, shopping lists, list items, checkout, orders, order status, and order history.

**Customer and Payments** — Customer profiles, delivery addresses, payment methods including Apple Pay, digital wallets, EBT/SNAP, and age/alcohol verification.

**Discovery** — Recipes, ingredients, and meal kits for developer platform integrations that drive shopping list creation.

**Reviews and Ratings** — Customer ratings and reviews of products and orders.

**Platform and Security** — API keys, tokens, and webhooks for developer integrations.

## Types Summary

| Category | Types |
|---|---|
| Retail Stores | Store, RetailStore, StoreLocation, StoreHours, StoreDepartment, StoreZone, Aisle |
| Products | Item, Product, ProductDetails, ProductImage, ProductCategory, ProductBrand |
| Nutrition and Labels | NutritionalInfo, FoodLabel, Certification, Organic |
| Pricing | PriceInfo, StorePricing, RegularPrice, SalePrice, UnitPrice, PerWeightPrice |
| Fulfillment | FulfillmentOption, DeliveryWindow, PickupWindow |
| Inventory | StoreInventory, StockLevel, ItemAvailability, Substitution, SubstitutionPreference |
| Orders | Order, Cart, CartItem, CartSummary, ShoppingList, ListItem, Checkout |
| Delivery | OrderFulfillment, Delivery, DeliveryDriver, DriverLocation, DeliveryProof, OrderStatus, OrderHistory |
| Discovery | Recipe, Ingredient, MealKit |
| Brands and Promotions | BrandPage, BrandPromotion, Coupon, SaleEvent |
| Customers | Customer, Address, DeliveryAddress |
| Payments | PaymentMethod, ApplePay, Wallet, EBT, SNAP |
| Verification | AlcoholVerification, AgeVerification |
| Feedback | Rating, Review |
| Platform | APIKey, Token, Webhook |

## GraphQL File

See `instacart-schema.graphql` for the full schema definition.
