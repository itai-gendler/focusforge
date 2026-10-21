---
kind: edge
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
- text: The Product restores the sharing choice when withdrawal cannot be confirmed.
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

# Retain visible sharing on failed withdrawal

## Trigger

The server cannot confirm withdrawal.

## Outcome

The sharing choice returns to on and the learner receives a retry explanation.
