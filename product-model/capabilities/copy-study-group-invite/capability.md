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

# Copy study group invite

Copy a private group’s invite code for sharing with intended members.
