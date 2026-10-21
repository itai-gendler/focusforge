---
kind: primary
routes:
  app: Android app
steps:
- text: An opted-in account has completed focus minutes in the current local week.
  kind: condition
  entities:
  - entity: account
    effect: reads
    facts:
    - Leaderboard sharing
    - Display name
    - Level
    - Avatar
  - entity: focus-session
    effect: reads
    facts:
    - Subject
    - Started at
    - Minutes
    - Label
    - Owner
  unattended: true
  contexts:
    app:
      place: android::linked::leaderboard
- text: The Product publishes the weekly name, minutes, level and optional photo.
  kind: product
  entities:
  - entity: leaderboard-entry
    effect: creates
    facts:
    - Name
    - Week
    - Minutes
    - Level
    - Photo
    - Rank
  contexts:
    app:
      place: android::linked::leaderboard
references:
- kind: code
  role: implementation
  target: lib/core/providers/social_providers.dart#leaderboardPublisherProvider
- kind: code
  role: implementation
  target: lib/core/services/leaderboard_service.dart#publish
---

# Publish a positive weekly score

## Trigger

An opted-in account has completed focus minutes in the current local week.

## Outcome

The Product publishes the account’s weekly name, minutes, level and optional photo.
