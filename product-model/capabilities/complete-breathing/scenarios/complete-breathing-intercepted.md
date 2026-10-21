---
kind: primary
routes:
  app: Android app
references:
- kind: code
  role: implementation
  target: android/app/src/main/kotlin/dev/focusforge/focusforge/shield/AppBlockingService.kt#showOverlay
- kind: code
  role: implementation
  target: lib/features/shield/breath_gate.dart#BreathGateScreen
steps:
- kind: actor
  actor: learner
  text: Choose the breathing action on the app pause.
  entities: []
  contexts:
    app:
      place: android::breathing
- kind: product
  actor: learner
  text: The Product starts the guided breathing exercise.
  entities:
  - entity: breath-encounter
    effect: changes
    facts:
    - Exercise complete
    from: Offered
    to: Breathing
  contexts:
    app:
      place: android::breathing
- kind: product
  actor: learner
  text: The Product completes three guided cycles and presents the decision.
  entities:
  - entity: breath-encounter
    effect: changes
    from: Breathing
    to: Ready
    facts:
    - Exercise complete
  contexts:
    app:
      place: android::breathing
---

# Complete the intercepted breathing exercise

## Trigger

The app pause offers a breathing exercise.

## Outcome

Three guided cycles finish and the exercise offers its decision.
