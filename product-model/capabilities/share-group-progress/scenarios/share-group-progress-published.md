---
kind: primary
routes:
  app: Android app
steps:
- text: A joined member’s completed minutes, name or focus status changes.
  kind: condition
  entities:
  - entity: focus-session
    effect: reads
    facts:
    - Subject
    - Started at
    - Minutes
    - Label
    - Owner
  - entity: focus-timer
    effect: reads
    facts:
    - Plan
    - Subject
    - Phase
    - Remaining time
    - Planned duration
    - Started at
    - Ends at
    - Cycle position
    - Starting account
    - Hidden duration
  - entity: account
    effect: reads
    facts:
    - Display name
  unattended: true
  contexts:
    app:
      place: android::linked::groups
- text: The Product updates that member’s current UTC-week summary in each joined group.
  kind: product
  entities:
  - entity: group-membership
    effect: changes
    facts:
    - Name
    - Week
    - Minutes
    - Focus until
  - entity: study-group
    effect: changes
    facts:
    - Week
    - Completed hours
    - Focusing now
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

# Publish the current group summary

## Trigger

A joined member’s completed minutes, name or focus status changes.

## Outcome

The Product updates that member’s current UTC-week summary in each joined group.
