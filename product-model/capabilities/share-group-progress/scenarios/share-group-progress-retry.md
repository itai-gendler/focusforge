---
kind: edge
routes:
  app: Android app
steps:
- text: The latest summary failed to sync.
  kind: condition
  entities:
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
  unattended: true
  contexts:
    app:
      place: android::linked::groups
- text: The Product retains local study progress, reports the pending sync and retries on a later refresh.
  kind: product
  entities:
  - entity: group-membership
    effect: reads
    facts:
    - Week
    - Minutes
  contexts:
    app:
      place: android::linked::groups
references:
- kind: code
  role: implementation
  target: lib/core/providers/social_providers.dart#groupPublisherProvider
- kind: code
  role: implementation
  target: lib/core/providers/social_providers.dart#groupWeekMinutesProvider
- kind: code
  role: implementation
  target: lib/core/services/study_group_service.dart#publish
---

# Retry a group summary

## Trigger

The latest summary failed to sync.

## Outcome

The Product retains local study progress, reports the pending sync and retries on a later refresh.
