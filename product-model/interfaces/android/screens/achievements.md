---
entities:
- entity: achievement
  shows:
  - Name
  - Target
  - Progress
  - Earned at
- entity: account
  shows:
  - Backup status
references:
- kind: code
  role: implementation
  target: lib/features/settings/achievements_screen.dart#AchievementsScreen
---

# Achievements

The badge cabinet: each badge’s target, measured progress and earned date.
