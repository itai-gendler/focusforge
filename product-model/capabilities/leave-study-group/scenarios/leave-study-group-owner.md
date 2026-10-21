---
kind: alternate
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
- text: The Product removes the departing membership and transfers group ownership.
  kind: product
  entities:
  - entity: group-membership
    effect: removes
    as: departing
  - entity: study-group
    effect: changes
    facts:
    - Owner
    - Member count
  - entity: group-membership
    as: successor
    effect: changes
    facts:
    - Role
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

# Leave as the group owner

## Trigger

The owner leaves a group that still has other members.

## Outcome

Ownership passes to the first remaining member and the departing row is removed.
