---
kind: validation
routes:
  app: Android app
steps:
- text: Enter allocations that differ from the selected total.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::home
- text: The Product keeps the editor open with the remaining difference.
  kind: product
  entities:
  - entity: daily-goal
    effect: reads
    facts:
    - Minutes
    - Subject allocations
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

# Reject an incomplete allocation split

## Trigger

Some subject allocations do not add up to the selected total.

## Outcome

The saved goal remains unchanged until the allocation matches.
