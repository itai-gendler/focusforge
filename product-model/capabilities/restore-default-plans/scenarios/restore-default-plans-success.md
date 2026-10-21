---
kind: primary
routes:
  app: Android app
steps:
- text: Choose Restore default plans.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::focus
- text: The Product restores the stock pace choices while retaining saved custom paces.
  kind: product
  entities:
  - entity: preferences
    effect: changes
    facts:
    - Hidden presets
  actor: learner
  contexts:
    app:
      place: android::focus
references:
- kind: code
  role: implementation
  target: lib/core/providers/study_providers.dart#restoreStock
- kind: code
  role: implementation
  target: lib/features/focus/focus_screen.dart#FocusScreen
---

# Restore default plans

## Trigger

Choose Restore default plans.

## Outcome

The Product restores the stock pace choices and preserves saved custom plans.
