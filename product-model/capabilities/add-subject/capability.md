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
domain: focus
---

# Add subject

Add a named study area with an identifying appearance and a starting weekly target.
