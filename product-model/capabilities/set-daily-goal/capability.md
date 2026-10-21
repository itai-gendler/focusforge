---
availability:
- place: android::local
- place: android::linked
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
domain: home
---

# Set daily goal

Save today’s target, optionally split it across subjects and repeat it through Sunday.
