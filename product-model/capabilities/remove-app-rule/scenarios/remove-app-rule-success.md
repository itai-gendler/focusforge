---
kind: primary
routes:
  app: Android app
steps:
- text: Choose to remove the app’s rule.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::shield
- text: The Product removes the selected app rule.
  kind: product
  entities:
  - entity: app-rule
    effect: removes
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

# Remove app rule

## Trigger

Choose to remove the app’s rule.

## Outcome

The Product removes the selected app rule.
