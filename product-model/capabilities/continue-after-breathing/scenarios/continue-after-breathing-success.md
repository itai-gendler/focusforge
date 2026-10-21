---
kind: primary
routes:
  app: Android app
steps:
- text: Choose the continuation after completing the exercise.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::breathing
- text: The Product opens the selected app for the offered access window and records one continuation decision.
  kind: product
  entities:
  - entity: breath-encounter
    effect: changes
    facts:
    - Decision
    - Time
    - Owner
    - Access until
    from: Ready
    to: Continued
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
  target: lib/core/services/shield_service.dart#ShieldConfig
---

# Continue after breathing

## Trigger

Choose the continuation after completing the exercise.

## Outcome

The Product opens the selected app for the offered access window and records one continuation decision.

## Edge cases

- A failed handoff keeps the flow open with a retryable explanation.
- Previewing the exercise creates no real app-access decision.
