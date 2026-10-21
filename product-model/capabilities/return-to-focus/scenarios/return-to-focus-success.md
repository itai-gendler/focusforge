---
kind: primary
routes:
  app: Android app
steps:
- text: Choose the offered return-to-focus action.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::breathing
- text: The Product records one walk-away decision and returns from the pause flow.
  kind: product
  entities:
  - entity: breath-encounter
    effect: changes
    facts:
    - Decision
    - Time
    - Owner
    from: Ready
    to: Walked away
  actor: learner
  contexts:
    app:
      place: android::breathing
references:
- kind: code
  role: implementation
  target: lib/features/shield/breath_gate.dart#BreathGateScreen
- kind: code
  role: implementation
  target: lib/core/providers/shield_providers.dart#BreathEventsNotifier
---

# Return to focus

## Trigger

Choose the offered return-to-focus action.

## Outcome

The Product records one walk-away decision and returns from the pause flow.

## Edge cases

- A preview encounter does not add a real decision to Shield history.
