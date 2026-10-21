---
kind: alternate
routes:
  app: Android app
steps:
- text: Select the suggested or another pace and choose Use this plan.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::setup
- text: The Product saves the starting pace without starting the clock.
  kind: product
  entities:
  - entity: focus-timer
    effect: changes
    facts:
    - Plan
    - Remaining time
    - Planned duration
    from: Ready
    to: Ready
  actor: learner
  contexts:
    app:
      place: android::setup
references:
- kind: code
  role: implementation
  target: lib/core/providers/study_providers.dart#setPreset
- kind: code
  role: implementation
  target: lib/features/focus/focus_screen.dart#FocusScreen
---

# Choose the starting pace

## Trigger

Setup reaches Choose your pace.

## Outcome

The starting pace is saved and setup proceeds to optional Usage Access.
