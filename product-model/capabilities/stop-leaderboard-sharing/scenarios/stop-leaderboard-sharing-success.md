---
kind: primary
routes:
  app: Android app
steps:
- text: Turn off Share my weekly score.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::linked::leaderboard
- text: The Product withdraws the account’s published rows and saves sharing as off.
  kind: product
  entities:
  - entity: leaderboard-entry
    effect: removes
  - entity: account
    effect: changes
    facts:
    - Leaderboard sharing
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

# Stop leaderboard sharing

## Trigger

Turn off Share my weekly score.

## Outcome

The Product withdraws the account’s published rows and saves sharing as off.
