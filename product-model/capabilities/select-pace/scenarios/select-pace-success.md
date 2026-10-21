---
kind: primary
routes:
  app: Android app
steps:
- text: Choose a different pace and confirm any unfinished-block warning.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::focus
- text: The Product prepares a fresh focus block in the chosen pace while retaining its study-area selection.
  kind: product
  entities:
  - entity: focus-timer
    effect: changes
    facts:
    - Plan
    - Phase
    - Remaining time
    - Planned duration
    - Cycle position
    - Hidden duration
    from: Running
    to: Ready
  actor: learner
  contexts:
    app:
      place: android::focus
references:
- kind: code
  role: implementation
  target: lib/core/providers/study_providers.dart#setPreset
- kind: code
  role: implementation
  target: lib/features/focus/focus_screen.dart#FocusScreen
---

# Select pace

## Trigger

Choose a different pace and confirm any unfinished-block warning.

## Outcome

The Product prepares a fresh focus block in the chosen pace while retaining the chosen subject.

## Edge cases

- Cancelling the warning leaves unfinished time and the chosen pace intact.
- Selecting the already selected pace leaves the timer intact.
