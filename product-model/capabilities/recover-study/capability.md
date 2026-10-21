---
availability:
- place: android::linked
references:
- kind: code
  role: implementation
  target: lib/core/services/study_backup_service.dart#connect
- kind: code
  role: implementation
  target: lib/core/services/firebase_auth_service.dart#FirebaseAuthService
- kind: code
  role: implementation
  target: lib/core/services/achievement_service.dart#mergeAchievementTimes
domain: account-privacy
---

# Recover study

Reconcile the linked identity’s completed sessions, settings and earned badges before applying a recovered account.
