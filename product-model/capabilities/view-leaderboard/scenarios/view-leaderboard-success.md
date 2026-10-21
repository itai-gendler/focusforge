---
kind: primary
routes:
  app: Android app
steps:
- text: Open the weekly leaderboard.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::linked::leaderboard
- text: The Product shows up to one hundred rows ordered by completed minutes and marks the learner’s own row.
  kind: product
  entities:
  - entity: leaderboard-entry
    effect: reads
    facts:
    - Name
    - Week
    - Minutes
    - Level
    - Photo
    - Rank
  actor: learner
  contexts:
    app:
      place: android::linked::leaderboard
references:
- kind: code
  role: implementation
  target: lib/core/providers/social_providers.dart#BoardOptInNotifier
- kind: code
  role: implementation
  target: lib/core/services/leaderboard_service.dart#FirebaseLeaderboardService
- kind: code
  role: implementation
  target: lib/features/settings/leaderboard_screen.dart#LeaderboardScreen
---

# View leaderboard

## Trigger

Open the weekly leaderboard.

## Outcome

The Product shows up to one hundred rows ordered by completed minutes and marks the current account’s row.

## Edge cases

- A zero-minute week does not create a named standing.
- Empty, unavailable and failed board reads have separate explanations; transient reads retry.
