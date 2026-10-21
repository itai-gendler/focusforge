---
availability:
- place: android::linked
references:
- kind: code
  role: implementation
  target: lib/core/services/study_backup_service.dart#StudyBackupService
- kind: code
  role: implementation
  target: lib/core/services/achievement_service.dart#FirebaseAchievementService
domain: account-privacy
---

# Back up study

Privately sync the linked account’s study setup, completed sessions and earned achievements; device usage and Shield activity remain local.
