---
kind: primary
routes:
  app: Android app
steps:
- text: Choose Reset and confirm any unfinished focus warning.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::focus
- text: The Product prepares a fresh block without creating completed study credit for the abandoned time.
  kind: product
  entities:
  - entity: focus-timer
    effect: changes
    facts:
    - Phase
    - Remaining time
    - Planned duration
    - Started at
    - Ends at
    from: Running
    to: Ready
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

# Reset focus timer

## Trigger

Choose Reset and confirm any unfinished focus warning.

## Outcome

The Product prepares a fresh block without creating completed study credit for the abandoned time.

## Edge cases

- Completed blocks and the cycle position remain.
- Cancelling the confirmation preserves the block.
