---
kind: primary
routes:
  app: Android app
steps:
- text: Choose Resume.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::focus
- text: The Product starts a new deadline from the paused remaining time and retains the original focus start.
  kind: product
  entities:
  - entity: focus-timer
    effect: changes
    facts:
    - Ends at
    - Remaining time
    from: Paused
    to: Running
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

# Resume focus timer

## Trigger

Choose Resume.

## Outcome

The Product starts a new deadline from the paused remaining time and retains the original focus start.
