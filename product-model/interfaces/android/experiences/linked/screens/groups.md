---
entities:
- entity: study-group
  shows:
  - Name
  - Weekly target
  - Invite code
  - Member count
  - Week
  - Completed hours
  - Focusing now
  collects:
  - Name
  - Weekly target
  - Invite code
- entity: group-membership
  shows:
  - Name
  - Week
  - Minutes
  - Focus until
references:
- kind: code
  role: implementation
  target: lib/features/settings/study_groups_screen.dart#StudyGroupsScreen
---

# Study groups

The learner’s private study groups: each group’s shared weekly target and progress, its invite code, member standings and who is focusing now, with creating, joining and leaving.
