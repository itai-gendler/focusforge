---
kind: primary
routes:
  app: Android app
steps:
- text: Enter a plan name, study goal and fixed length or random range.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::focus
- text: The Product saves the custom plan with derived breaks and makes it the selected pace.
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
  - entity: focus-timer
    effect: changes
    facts:
    - Plan
    - Planned duration
    - Remaining time
    - Hidden duration
    from: Ready
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

# Create custom plan

## Trigger

Enter a plan name, study goal and fixed length or random range.

## Outcome

The Product saves the custom plan with derived breaks and makes it the selected pace.

## Edge cases

- The name is normalized and limited to forty characters.
- A random range requires a minimum below its maximum.
