---
kind: primary
routes:
  app: Android app
steps:
- text: Confirm Leave group.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::linked::groups
- text: The Product removes the learner’s membership and updates the group member count.
  kind: product
  entities:
  - entity: group-membership
    effect: removes
  - entity: study-group
    effect: changes
    facts:
    - Member count
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

# Leave study group

## Trigger

Confirm Leave group.

## Outcome

The Product removes the learner’s membership and updates the group member count.
