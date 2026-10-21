---
appliesTo:
- type: entity
  id: daily-goal
references:
- kind: code
  role: implementation
  target: lib/core/models/focus_goal.dart#FocusGoalPlan
- kind: code
  role: implementation
  target: lib/core/providers/goal_planner_providers.dart#FocusGoalPlannerNotifier
---

# Subject allocations must exactly equal the daily goal

A saved daily target is positive and at most 720 minutes. The optional split is either empty or totals exactly that target. Repeat through Sunday applies the same daily target on each eligible date; it is not a weekly pool.
