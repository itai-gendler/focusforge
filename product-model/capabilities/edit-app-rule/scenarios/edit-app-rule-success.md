---
kind: primary
routes:
  app: Android app
steps:
- text: Choose a tier or edit the daily budget.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::shield
- text: The Product saves the chosen tier and the daily allowance for budgeted use.
  kind: product
  entities:
  - entity: app-rule
    effect: changes
    facts:
    - Tier
    - Daily budget
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

# Edit app rule

## Trigger

Choose a tier or edit the daily budget.

## Outcome

The Product saves the chosen tier and the daily allowance for budgeted use.

## Edge cases

- Budget changes are bounded to five through one thousand four hundred forty minutes.
- Always allowed, Time budgeted, Blocked and Only while focusing are values of one policy choice.
