---
kind: primary
routes:
  app: Android app
steps:
- text: Open a joined group.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::linked::groups
- text: The Product presents the group total and member progress for the current UTC week.
  kind: product
  entities:
  - entity: study-group
    effect: reads
    facts:
    - Name
    - Weekly target
    - Invite code
    - Owner
    - Member count
    - Week
    - Completed hours
    - Focusing now
  - entity: group-membership
    effect: reads
    facts:
    - Name
    - Role
    - Joined at
    - Week
    - Minutes
    - Focus until
    - Invite accepted
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
- kind: code
  role: implementation
  target: lib/core/providers/social_providers.dart#groupWeekProvider
---

# View study groups

## Trigger

Open a joined group.

## Outcome

The Product presents the group total and member progress for the current UTC week.

## Edge cases

- A member’s older-week row contributes zero to the current weekly total.
- A loading or failed member query is distinguished from a measured zero; the learner can retry.
- Expired focus deadlines no longer show Focusing now.
