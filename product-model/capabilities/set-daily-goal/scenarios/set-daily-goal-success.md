---
kind: primary
routes:
  app: Android app
steps:
- text: Choose a positive daily target and optionally split it evenly or enter allocations.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::home
- text: The Product saves the date, target and exact allocation split only after persistence succeeds.
  kind: product
  entities:
  - entity: daily-goal
    effect: creates
    facts:
    - Date
    - Minutes
    - Subject allocations
    - Repeat through Sunday
    - Progress
    - Completed progress
  actor: learner
  contexts:
    app:
      place: android::home
references:
- kind: code
  role: implementation
  target: lib/core/providers/goal_planner_providers.dart#FocusGoalPlannerNotifier
- kind: code
  role: implementation
  target: lib/core/models/focus_goal.dart#FocusGoalPlan
- kind: code
  role: implementation
  target: lib/features/dashboard/widgets/daily_goal_sheet.dart#showDailyGoalSheet
---

# Set daily goal

## Trigger

Choose a positive daily target and optionally split it evenly or enter subject allocations.

## Outcome

The Product saves the date, target and exact allocation split only after persistence succeeds.

## Edge cases

- If any subject minutes are assigned, their sum must equal the target.
- A failed save leaves the editor open and the previous saved goal active.
