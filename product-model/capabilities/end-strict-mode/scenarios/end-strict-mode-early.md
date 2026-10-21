---
kind: primary
routes:
  app: Android app
steps:
- text: Enter the commitment phrase, wait for the cooldown and confirm End the lock.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::strict-mode
- text: The Product closes the commitment window.
  kind: product
  entities:
  - entity: strict-mode
    effect: changes
    facts:
    - Started at
    - Ends at
    from: Active
    to: 'Off'
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

# End Strict Mode

## Trigger

Enter the commitment phrase, wait for the cooldown and confirm End the lock.

## Outcome

The Product closes the commitment window.

## Edge cases

- The final confirmation remains unavailable until the cooldown elapses.
- Cancelling the flow preserves the active commitment.
