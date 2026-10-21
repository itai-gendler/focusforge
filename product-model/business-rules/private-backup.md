---
appliesTo:
- type: capability
  id: back-up-study
- type: capability
  id: recover-study
- type: entity
  id: account
  facts:
  - Backup status
references:
- kind: code
  role: implementation
  target: lib/core/services/study_backup_service.dart#StudyBackupService
- kind: code
  role: implementation
  target: lib/core/services/achievement_service.dart#FirebaseAchievementService
---

# Private backup contains study records and excludes device usage

Connected accounts privately save profile, subjects, custom plans, goals, completed sessions and earned badges. App usage and Shield activity stay local. Offline changes remain local until syncing succeeds.
