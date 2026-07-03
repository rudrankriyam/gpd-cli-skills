---
name: gpd-id-resolver
description: Resolve Google Play identifiers (package, tracks, version codes, products, subscriptions) using gpd. Use when commands require IDs or exact values.
---

# GPD ID Resolver

Use this skill to map names to IDs needed by other gpd commands.

## Package name (app ID)
- Package name is the primary identifier: `com.example.app`.
- Always pass `--package` explicitly for deterministic results.
- This resolver skill is read-only. Use only `list`, `get`, or status-style commands here; do not run mutating commands while resolving IDs.

## Track names
- Common tracks: `internal`, `alpha`, `beta`, `production`.
- List tracks:
  - `gpd publish tracks --package com.example.app`

## Version codes and release status
- Use release status to find version codes on a track:
  - `gpd publish status --package com.example.app --track production`

## Tester groups
- List testers by track:
  - `gpd publish testers list --package com.example.app --track internal`

## Monetization IDs
- Products:
  - `gpd monetization products list --package com.example.app`
  - `gpd monetization products get sku123 --package com.example.app`
- One-time products:
  - `gpd monetization onetimeproducts list --package com.example.app`
- Subscriptions:
  - `gpd monetization subscriptions list --package com.example.app`
  - `gpd monetization subscriptions get sub123 --package com.example.app`
- Base plans and offers:
  - `gpd monetization subscriptions get sub123 --package com.example.app`
  - `gpd monetization offers list --package com.example.app sub123 plan456`

## Permissions IDs
- Developer users:
  - `gpd permissions users list --developer-id DEV_ID`
- App grants:
  - Resolve the package name and user email with read-only commands before using a permissions-management skill for grant changes.

## Output tips
- JSON is default; use `--pretty` for debugging.
- Use `--all` on list commands to avoid missing items.
