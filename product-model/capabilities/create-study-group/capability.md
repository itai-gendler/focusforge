---
availability:
- place: android::linked
references:
- kind: code
  role: implementation
  target: lib/core/services/study_group_service.dart#FirebaseStudyGroupService
- kind: code
  role: implementation
  target: lib/features/settings/study_groups_screen.dart#StudyGroupsScreen
- kind: code
  role: implementation
  target: firestore.rules
domain: study-groups
---

# Create study group

Create a private study group after accepting community terms, with a shared weekly target.
