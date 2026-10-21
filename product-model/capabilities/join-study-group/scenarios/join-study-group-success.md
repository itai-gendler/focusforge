---
kind: primary
routes:
  app: Android app
steps:
- text: Accept the terms and enter the shared ten-character invite code.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::linked::groups
- text: The Product adds the learner’s membership to the invited group.
  kind: product
  entities:
  - entity: group-membership
    effect: creates
    facts:
    - Name
    - Role
    - Joined at
    - Week
    - Minutes
    - Focus until
    - Invite accepted
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

# Join study group

## Trigger

Accept the terms and enter the shared ten-character invite code.

## Outcome

The Product adds the learner’s membership to the invited group.

## Edge cases

- Spaces and hyphens are removed and letters are uppercased.
- An invalid or expired invite leaves membership unchanged.
- The UI detects an already joined group; groups hold at most thirty-two members.
