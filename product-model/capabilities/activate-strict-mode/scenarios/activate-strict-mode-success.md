---
kind: primary
routes:
  app: Android app
steps:
- text: Enter the commitment phrase, wait for the cooldown and confirm Lock it in.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::strict-mode
- text: The Product begins the timed commitment window.
  kind: product
  entities:
  - entity: strict-mode
    effect: changes
    facts:
    - Started at
    - Ends at
    from: 'Off'
    to: Active
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

# Activate Strict Mode

## Trigger

Enter the commitment phrase, wait for the cooldown and confirm Lock it in.

## Outcome

The Product begins the timed commitment window.

## Edge cases

- Dismissing at any stage leaves the saved activation state unchanged.
- The phrase is compared after trimming and without case sensitivity.
