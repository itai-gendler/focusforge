---
availability:
- place: android::local
- place: android::linked
references:
- kind: code
  role: implementation
  target: lib/core/providers/study_providers.dart#rangeBarsProvider
- kind: code
  role: implementation
  target: lib/core/providers/study_providers.dart#daySummaryProvider
- kind: code
  role: implementation
  target: lib/core/providers/goal_planner_providers.dart#activeFocusGoalSecondsProvider
- kind: code
  role: implementation
  target: lib/features/dashboard/dashboard_screen.dart#DashboardScreen
domain: home
---

# View study progress

Review completed study by day, local week or current month, including subjects, current streak and live daily goal progress.
