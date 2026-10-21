---
entities:
- entity: leaderboard-entry
  shows:
  - Name
  - Week
  - Minutes
  - Level
  - Photo
  - Rank
- entity: account
  shows:
  - Leaderboard sharing
  - Display name
  - Level
references:
- kind: code
  role: implementation
  target: lib/features/settings/leaderboard_screen.dart#LeaderboardScreen
---

# Leaderboard

This week’s opt-in standings, the learner’s own row and the Share my weekly score choice.
