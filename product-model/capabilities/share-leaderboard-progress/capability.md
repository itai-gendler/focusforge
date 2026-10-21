---
availability:
- place: android::linked
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
domain: leaderboard
---

# Share leaderboard progress

Opt in to publishing a named weekly summary after accepting community terms.
