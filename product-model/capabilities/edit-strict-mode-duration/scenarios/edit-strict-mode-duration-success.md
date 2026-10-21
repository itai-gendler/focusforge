---
kind: primary
routes:
  app: Android app
steps:
- text: Choose a lock length.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::strict-mode
- text: The Product saves the lock length for the commitment window.
  kind: product
  entities:
  - entity: strict-mode
    effect: changes
    facts:
    - Duration
  actor: learner
  contexts:
    app:
      place: android::strict-mode
references:
- kind: code
  role: implementation
  target: lib/features/settings/strict_mode_screen.dart#StrictModeScreen
- kind: code
  role: implementation
  target: lib/core/providers/shield_providers.dart#StrictModeNotifier
---

# Edit Strict Mode duration

## Trigger

Choose a lock length.

## Outcome

The Product saves the lock length for the commitment window.
