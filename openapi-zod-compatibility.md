---
name: OpenAPI Zod compatibility
description: Compatibility constraint between Orval-generated Zod schemas and the workspace dependency version.
---

The OpenAPI generator can emit newer Zod convenience APIs such as `z.int()` and `z.email()` even when the workspace resolves Zod 3.x. Prefer schema shapes that generate broadly compatible validators, or align the dependency before adding those formats.

**Why:** Code generation can succeed while the chained library typecheck fails, which blocks the generated client from being consumed by the app.

**How to apply:** After changing the OpenAPI contract, run codegen and the library typecheck before implementing server routes or wiring frontend hooks.