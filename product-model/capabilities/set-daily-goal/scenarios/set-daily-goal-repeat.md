---
kind: alternate
routes:
  app: Android app
steps:
- text: Select Repeat through Sunday and save.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::home
- text: The Product saves the repeated daily goal and its date-bounded applicability.
  kind: product
  entities:
  - entity: daily-goal
    effect: changes
    facts:
    - Date
    - Minutes
    - Subject allocations
    - Repeat through Sunday
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

# Repeat the daily goal through Sunday

## Trigger

A daily goal is being saved.

## Outcome

The same target applies separately on each remaining day through Sunday.
