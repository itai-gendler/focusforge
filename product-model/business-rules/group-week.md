---
appliesTo:
- type: entity
  id: study-group
- type: entity
  id: group-membership
references:
- kind: code
  role: implementation
  target: lib/core/providers/social_providers.dart#groupWeekMinutesProvider
- kind: code
  role: implementation
  target: lib/features/settings/study_groups_screen.dart#_GroupCard
---

# Study-group progress uses a UTC Monday week

Shared group totals use completed minutes from Monday 00:00 UTC through the current moment. Older-week member rows count as zero in current standings. A shared focus deadline counts as active only while it remains in the future.
