---
availability:
- place: android::local
- place: android::linked
references:
- kind: code
  role: implementation
  target: lib/core/providers/social_providers.dart#AchievementsNotifier
- kind: code
  role: implementation
  target: lib/core/providers/social_providers.dart#_measure
- kind: code
  role: implementation
  target: lib/core/services/achievement_service.dart#mergeAchievementTimes
domain: achievements
---

# Earn achievement

Measure badge progress and retain an award once its threshold is reached.
