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
- kind: code
  role: implementation
  target: lib/core/providers/social_providers.dart#groupWeekProvider
domain: study-groups
---

# View study groups

Review joined groups, their shared weekly goal, member standings and current focus presence.
