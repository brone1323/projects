# Technical Architecture — Luxury Streetwear

## Architecture Principle

The storefront should not depend on Shopify as the customer-facing website.

The supplier should be treated as a fulfillment backend behind our own system.

## Target Flow

```txt
Customer
  ↓
Custom Website
  ↓
Backend API
  ↓
Database
  ↓
Supplier Integration Layer
  ↓
Supplier Fulfillment
  ↓
Tracking Returned To Customer
```

## Core Components

### Web App

Premium customer-facing ecommerce site.

Likely stack:
- Next.js
- React
- Tailwind or custom CSS system
- Stripe checkout or custom checkout flow

### Admin App

Internal dashboard for managing:
- Products
- Collections
- Orders
- Customers
- Fulfillment status
- Supplier sync
- Content
- AI agent reports

### API Package

Responsible for:
- Product APIs
- Cart APIs
- Order APIs
- Customer APIs
- Supplier orchestration
- Webhooks

### Database Package

Responsible for:
- Product schema
- Variant schema
- Supplier product mapping
- Order schema
- Customer schema
- Fulfillment events

### Supplier Package

Do not hardcode supplier logic into the storefront.

Create an interface such as:

```ts
interface SupplierProvider {
  listProducts(): Promise<SupplierProduct[]>;
  getProduct(id: string): Promise<SupplierProduct>;
  createOrder(order: SupplierOrderInput): Promise<SupplierOrderResult>;
  getOrderStatus(orderId: string): Promise<SupplierOrderStatus>;
  getTracking(orderId: string): Promise<SupplierTrackingResult>;
}
```

Then implement:

```txt
packages/suppliers/apliiq
```

## Future Supplier Strategy

Apliiq should be replaceable later with:

- Another POD supplier.
- A private-label manufacturer.
- A small-batch cut-and-sew supplier.
- A warehouse/3PL.

## AI Agent Targets

Agents should eventually support:

- Catalog updates.
- Product copy.
- SEO content.
- Fulfillment monitoring.
- Delayed order alerts.
- Supplier issue reports.
- Competitive research.
