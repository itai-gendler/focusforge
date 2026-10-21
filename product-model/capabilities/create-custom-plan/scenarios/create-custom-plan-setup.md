---
kind: alternate
routes:
  app: Android app
steps:
- text: Enter a custom study goal and pace.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::setup
- text: The Product saves the custom plan for selection.
  kind: product
  entities:
  - entity: custom-plan
    effect: creates
    facts:
    - Name
    - Study goal
    - Focus length
    - Random range
    - Short break
    - Long break
    - Cadence
    - Planned blocks
  actor: learner
  contexts:
    app:
      place: android::setup
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

# Create a starting custom plan

## Trigger

The starting pace stage offers a custom plan.

## Outcome

The saved custom pace becomes the pending starting choice.
