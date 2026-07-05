# Task 001 — Codex Start Here

## Context

You are working on a custom luxury streetwear ecommerce platform.

This is not a Shopify theme project. The goal is to build a premium custom website and backend that can connect to supplier fulfillment APIs.

## First Objective

Create a development plan and project scaffold for this repository.

## Requirements

- Use a monorepo-friendly structure.
- Include a custom customer-facing web app.
- Include an admin dashboard.
- Include shared packages for API, database, UI, and supplier integrations.
- Supplier logic must be abstracted behind a provider interface.
- Do not hardcode Apliiq into the frontend.
- Do not build a generic product grid-first Shopify clone.

## Suggested Structure

```txt
apps/
  web/
  admin/

packages/
  api/
  db/
  suppliers/
    core/
    apliiq/
  ui/
```

## Deliverables

1. Propose the final stack.
2. Create the initial app/package structure.
3. Add environment variable examples.
4. Add a supplier provider interface.
5. Add placeholder implementation for Apliiq.
6. Add README setup instructions.

## Important

Before coding, read:

- `businesses/01-luxury-streetwear/README.md`
- `businesses/01-luxury-streetwear/supplier-due-diligence.md`
- `businesses/01-luxury-streetwear/launch-collection.md`
- `businesses/01-luxury-streetwear/technical-architecture.md`
