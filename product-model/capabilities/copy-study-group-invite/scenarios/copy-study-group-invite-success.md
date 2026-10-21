---
kind: primary
routes:
  app: Android app
steps:
- text: Choose the invite code.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::linked::groups
- text: The Product copies the group code to the clipboard.
  kind: product
  entities:
  - entity: study-group
    effect: reads
    facts:
    - Invite code
  actor: learner
  contexts:
    app:
      place: android::linked::groups
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
---

# Copy study group invite

## Trigger

Choose the invite code.

## Outcome

The Product copies the group code to the clipboard.
