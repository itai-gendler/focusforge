---
appliesTo:
- type: entity
  id: subject
- type: entity
  id: focus-session
- type: entity
  id: daily-goal
references:
- kind: code
  role: implementation
  target: lib/core/providers/study_providers.dart#SubjectsNotifier
- kind: code
  role: implementation
  target: lib/core/providers/goal_planner_providers.dart#removeSubjectAllocation
---

# Removing a subject retains completed study

Removing a subject preserves completed minutes and records its old name for history. If the subject occurs in a daily allocation, the entire allocation split is cleared while the overall target remains.
