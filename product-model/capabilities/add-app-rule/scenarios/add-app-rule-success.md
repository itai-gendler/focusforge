---
kind: primary
routes:
  app: Android app
steps:
- text: Choose an installed app and its desired rule.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::shield
- text: The Product saves the app rule with its tier and applicable budget.
  kind: product
  entities:
  - entity: app-rule
    effect: creates
    facts:
    - App
    - Tier
    - Daily budget
    - Used today
  actor: learner
  contexts:
    app:
      place: android::shield
references:
- kind: code
  role: implementation
  target: lib/core/providers/shield_providers.dart#WhitelistNotifier
- kind: code
  role: implementation
  target: lib/features/shield/shield_screen.dart#ShieldScreen
- kind: code
  role: implementation
  target: lib/features/shield/shield_access.dart#ensureShieldAccess
---

# Add app rule

## Trigger

Choose an installed app and its desired rule.

## Outcome

The Product saves the app rule with its tier and applicable budget.

## Edge cases

- Selecting an already listed app changes its tier instead of creating a duplicate.
- New Time budgeted rules default to thirty minutes.
