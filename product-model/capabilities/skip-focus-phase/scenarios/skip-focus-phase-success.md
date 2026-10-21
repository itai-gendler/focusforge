---
kind: primary
routes:
  app: Android app
steps:
- text: Choose Skip and confirm any unfinished focus warning.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::focus
- text: The Product advances to the next phase with the existing running or paused condition.
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
    - Cycle position
    from: Running
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

# Skip focus phase

## Trigger

Choose Skip and confirm any unfinished focus warning.

## Outcome

The Product advances to the next phase with the existing running or paused condition.

## Edge cases

- Skipping a focus phase advances cycle position but grants no focus minutes or XP.
- Skipping a break prepares the next focus phase.
