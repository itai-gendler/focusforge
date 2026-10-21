---
appliesTo:
- type: entity
  id: leaderboard-entry
- type: entity
  id: account
  facts:
  - Leaderboard sharing
references:
- kind: code
  role: implementation
  target: lib/core/providers/social_providers.dart#leaderboardPublisherProvider
- kind: code
  role: implementation
  target: lib/core/services/leaderboard_service.dart#withdraw
---

# Leaderboard publication requires opt-in and positive weekly progress

Sharing is off initially. A linked learner can read standings without publishing. Publication starts only with opt-in and positive owned completed minutes in the current local Monday week. Sign-out leaves existing rows visible; successful opt-out withdraws published rows across weeks.
