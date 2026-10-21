---
appliesTo:
- type: entity
  id: focus-session
- type: entity
  id: daily-goal
- type: capability
  id: view-study-progress
references:
- kind: code
  role: implementation
  target: lib/core/providers/study_providers.dart#daySessionsProvider
- kind: code
  role: implementation
  target: lib/core/providers/goal_planner_providers.dart#activeFocusGoalSecondsProvider
---

# A focus session belongs to its starting calendar day

Completed personal study is assigned by the block’s start time. Personal weeks begin Monday in local time, and the current month contains dates through today. A daily goal may show the owned in-flight focus block before that time is saved as completed study.
