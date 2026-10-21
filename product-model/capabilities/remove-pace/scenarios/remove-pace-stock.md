---
kind: primary
routes:
  app: Android app
steps:
- text: Choose Remove on a stock preset.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::focus
- text: The Product hides the chosen preset while retaining at least one usable pace.
  kind: product
  entities:
  - entity: preferences
    effect: changes
    facts:
    - Hidden presets
  - entity: focus-timer
    effect: changes
    facts:
    - Plan
    - Remaining time
    - Phase
    from: Running
    to: Ready
  actor: learner
  contexts:
    app:
      place: android::focus
references:
- kind: code
  role: implementation
  target: lib/core/providers/study_providers.dart#PlanLibraryNotifier
- kind: code
  role: implementation
  target: lib/features/focus/focus_screen.dart#FocusScreen
---

# Remove preset

## Trigger

Choose Remove on a stock preset.

## Outcome

The Product hides the chosen preset while retaining at least one usable pace.

## Edge cases

- Removing the current preset requires confirming loss of unfinished time.
- Removing another preset preserves the running block.
