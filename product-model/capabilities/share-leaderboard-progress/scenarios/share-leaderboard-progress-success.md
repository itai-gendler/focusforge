---
kind: primary
routes:
  app: Android app
steps:
- text: Accept the community terms and turn on Share my weekly score.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::linked::leaderboard
- text: The Product saves the sharing choice; completed positive weekly progress can then be published.
  kind: product
  entities:
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

# Share leaderboard progress

## Trigger

Accept the community terms and turn on Share my weekly score.

## Outcome

The Product saves the sharing choice; completed positive weekly progress can then be published.
