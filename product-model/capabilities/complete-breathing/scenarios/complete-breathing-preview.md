---
kind: alternate
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
  text: Choose Preview the pause screen.
  entities: []
  contexts:
    app:
      place: android::shield
- kind: product
  actor: learner
  text: The Product starts a practice exercise without an actual app decision.
  entities: []
  contexts:
    app:
      place: android::breathing
- kind: product
  actor: learner
  text: The Product completes the practice exercise without recording a real decision.
  entities: []
  contexts:
    app:
      place: android::breathing
---

# Preview the breathing exercise

## Trigger

The learner tries the breathing preview in Shield.

## Outcome

The practice exercise runs for three guided cycles; it adds no actual encounter or shared progress.
