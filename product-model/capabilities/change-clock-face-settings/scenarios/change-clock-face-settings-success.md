---
kind: primary
routes:
  app: Android app
steps:
- text: Choose a clock face.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::clock-face
- text: The Product saves the clock preference.
  kind: product
  entities:
  - entity: preferences
    effect: changes
    facts:
    - Clock face
  actor: learner
  contexts:
    app:
      place: android::clock-face
references:
- kind: code
  role: implementation
  target: lib/core/providers/app_providers.dart#ClockFaceNotifier
- kind: code
  role: implementation
  target: lib/features/settings/clock_face_screen.dart#ClockFaceScreen
---

# Change clock face settings

## Trigger

Choose a clock face.

## Outcome

The Product saves the clock preference.
