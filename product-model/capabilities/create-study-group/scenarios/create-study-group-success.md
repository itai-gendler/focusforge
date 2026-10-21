---
kind: primary
routes:
  app: Android app
steps:
- text: Accept the community terms, enter a name and choose a weekly target.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::linked::groups
- text: The Product creates the private group, its invite code and the creator’s owner membership.
  kind: product
  entities:
  - entity: study-group
    effect: creates
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
    effect: creates
    facts:
    - Name
    - Role
    - Joined at
    - Week
    - Minutes
    - Focus until
    - Invite accepted
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

# Create study group

## Trigger

Accept the community terms, enter a name and choose a weekly target.

## Outcome

The Product creates the private group, its invite code and the creator’s owner membership.

## Edge cases

- Names must have one through sixty characters; targets must be whole hours from one through one thousand.
- Connection failure leaves an actionable error; a delayed request may still finish.
