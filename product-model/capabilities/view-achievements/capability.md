---
availability:
- place: android::local
- place: android::linked
references:
- kind: code
  role: implementation
  target: lib/features/settings/achievements_screen.dart#AchievementsScreen
- kind: code
  role: implementation
  target: lib/core/providers/social_providers.dart#AchievementsNotifier
domain: achievements
---

# View achievements

Review earned badges and progress remaining toward locked badges.
