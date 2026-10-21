---
kind: primary
routes:
  app: Android app
steps:
- text: Confirm removal of a saved custom pace.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::focus
- text: The Product removes the custom plan; removing the selected pace selects the first remaining plan and resets its unfinished block.
  kind: product
  entities:
  - entity: custom-plan
    effect: removes
  - entity: focus-timer
    effect: changes
    facts:
    - Plan
    - Phase
    - Planned duration
    - Remaining time
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
  target: lib/core/models/study.dart#CustomPlan
- kind: code
  role: implementation
  target: lib/features/focus/custom_plan_sheet.dart#showCustomPlanSheet
---

# Remove custom plan

## Trigger

Confirm removal of a saved custom pace.

## Outcome

The Product removes the custom plan; removing the selected pace selects the first remaining plan and resets its unfinished block.

## Edge cases

- The last usable plan cannot be removed.
- Removing a different plan preserves the current block and its stable plan selection.
