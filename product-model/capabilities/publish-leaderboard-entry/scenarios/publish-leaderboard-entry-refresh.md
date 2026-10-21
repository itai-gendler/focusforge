---
kind: alternate
routes:
  app: Android app
steps:
- text: An already published weekly summary changes.
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
- text: The Product replaces the current weekly summary with the latest completed total and shared profile.
  kind: product
  entities:
  - entity: leaderboard-entry
    effect: changes
    facts:
    - Name
    - Minutes
    - Level
    - Photo
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

# Refresh a weekly score

## Trigger

An already published weekly summary changes.

## Outcome

The Product replaces the current weekly summary with the latest completed total and shared profile.
