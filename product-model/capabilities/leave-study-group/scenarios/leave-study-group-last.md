---
kind: alternate
routes:
  app: Android app
steps:
- text: Confirm Leave group as the last member.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::linked::groups
- text: The Product removes the empty group and its final membership.
  kind: product
  entities:
  - entity: study-group
    effect: removes
  - entity: group-membership
    effect: removes
    with: study-group
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

# Close the group on final departure

## Trigger

The only remaining member leaves.

## Outcome

The group, its invite and final membership are removed.
