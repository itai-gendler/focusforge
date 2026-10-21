---
availability:
- place: android::local
- place: android::linked
references:
- kind: code
  role: implementation
  target: lib/features/focus/subject_picker.dart
- kind: code
  role: implementation
  target: lib/core/providers/study_providers.dart#setSubject
domain: focus
---

# Select subject

Choose the subject for the current timer or choose unassigned study.
