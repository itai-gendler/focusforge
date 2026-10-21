---
kind: primary
routes:
  app: Android app
steps:
- text: Edit the saved pace and confirm an unfinished-block warning when shown.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::focus
- text: The Product saves the edited pace and resets its unfinished block when timing changes.
  kind: product
  entities:
  - entity: custom-plan
    effect: changes
    facts:
    - Name
    - Study goal
    - Focus length
    - Random range
    - Short break
    - Long break
    - Cadence
    - Planned blocks
  - entity: focus-timer
    effect: changes
    facts:
    - Plan
    - Planned duration
    - Remaining time
    - Phase
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
  target: lib/core/providers/study_providers.dart#PlanLibraryNotifier
- kind: code
  role: implementation
  target: lib/core/models/study.dart#CustomPlan
- kind: code
  role: implementation
  target: lib/features/focus/custom_plan_sheet.dart#showCustomPlanSheet
---

# Edit custom plan

## Trigger

Edit the saved custom plan and confirm an unfinished-block warning when shown.

## Outcome

The Product saves the edited pace and resets its unfinished block when timing changes.

## Edge cases

- Completed study history remains saved.
- Cancelling the unfinished-block confirmation keeps the running block.
