---
kind: alternate
routes:
  app: Linked account
steps:
- text: An update or restart retains a matching verified linked credential and profile.
  kind: condition
  entities:
  - entity: account
    effect: reads
    facts:
    - Display name
    - Persona
    - Focus intention
    - Avatar
    - Setup complete
    - Email
    - Email verified
    - Cloud available
    - Backup status
    - Leaderboard sharing
    - XP
    - Level
    - Completed blocks
    - Focus hours
    - Current streak
    - Hidden members
  unattended: true
  contexts:
    app:
      place: android::linked::privacy
- text: The Product keeps local study available and reconciles private study in the background.
  kind: product
  entities:
  - entity: account
    effect: changes
    facts:
    - Backup status
  contexts:
    app:
      place: android::linked::privacy
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
---

# Reconcile a retained login

## Trigger

An update or restart retains a matching verified linked credential and profile.

## Outcome

The Product keeps local study available and reconciles private study in the background.
