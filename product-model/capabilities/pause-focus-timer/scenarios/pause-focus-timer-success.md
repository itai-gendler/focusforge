---
kind: primary
routes:
  app: Android app
steps:
- text: Choose Pause.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::focus
- text: The Product pauses the deadline and preserves the current phase and completed history.
  kind: product
  entities:
  - entity: focus-timer
    effect: changes
    facts:
    - Ends at
    - Remaining time
    from: Running
    to: Paused
  actor: learner
  contexts:
    app:
      place: android::focus
references:
- kind: code
  role: implementation
  target: lib/core/providers/study_providers.dart#TimerNotifier
- kind: code
  role: implementation
  target: lib/features/focus/focus_screen.dart#FocusScreen
---

# Pause focus timer

## Trigger

Choose Pause.

## Outcome

The Product pauses the deadline and preserves the current phase and completed history.
