---
availability:
- place: android::local
- place: android::linked
references:
- kind: code
  role: implementation
  target: lib/core/providers/study_providers.dart#SubjectsNotifier
- kind: code
  role: implementation
  target: lib/features/focus/manage_subjects_sheet.dart#showManageSubjectsSheet
- kind: code
  role: implementation
  target: lib/core/models/subject_naming.dart#SubjectNaming
- kind: code
  role: implementation
  target: lib/core/providers/goal_planner_providers.dart#removeSubjectAllocation
domain: focus
---

# Remove subject

Remove a subject while preserving the study history already completed under it.
