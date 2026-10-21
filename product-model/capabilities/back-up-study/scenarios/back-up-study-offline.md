---
kind: edge
routes:
  app: Linked account
steps:
- text: A private backup attempt cannot reach the account service.
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
- text: The Product retains the local changes pending a successful later sync.
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
  target: lib/core/services/study_backup_service.dart#StudyBackupService
- kind: code
  role: implementation
  target: lib/core/services/achievement_service.dart#FirebaseAchievementService
---

# Retain unsynced changes

## Trigger

A private backup attempt cannot reach the account service.

## Outcome

The Product retains the local changes pending a successful later sync.
