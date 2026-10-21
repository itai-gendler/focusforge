---
kind: primary
routes:
  app: Android app
steps:
- text: Open the clock view.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::focus
- text: The Product presents the current phase and visible countdown, or the Random focus indication.
  kind: product
  entities:
  - entity: focus-timer
    effect: reads
    facts:
    - Subject
    - Phase
    - Remaining time
    - Hidden duration
  actor: learner
  contexts:
    app:
      place: android::focus
references:
- kind: code
  role: implementation
  target: lib/features/focus/fullscreen_clock.dart#showFullscreenClock
- kind: code
  role: implementation
  target: lib/features/focus/focus_screen.dart#FocusScreen
---

# View focus clock

## Trigger

Open the clock view.

## Outcome

The Product presents the current phase and visible countdown, or the Random focus indication.
