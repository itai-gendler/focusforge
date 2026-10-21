---
appliesTo:
- type: entity
  id: achievement
- type: entity
  id: focus-session
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
---

# Earned badges retain their earliest known unlock date

Badge progress is measured from completed owned study, subject targets and walk-aways. Streak badges use the longest run of completed local-calendar days. Once earned, a badge stays earned despite a later streak lapse or local analytics clear. Private reconciliation unions earned badges and prefers the earliest known date.
