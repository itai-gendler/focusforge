---
kind: primary
routes:
  app: Linked account
steps:
- text: A confirmed linked identity is restored.
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
- text: The Product merges completed sessions by identity, chooses the latest settings snapshot and retains the earliest known earned badge dates.
  kind: product
  entities:
  - entity: account
    effect: changes
    facts:
    - Backup status
    - Display name
    - Persona
    - Avatar
    - Setup complete
    - XP
    - Level
    - Completed blocks
    - Focus hours
    - Leaderboard sharing
  - entity: subject
    effect: creates
    facts:
    - Name
    - Appearance
    - Weekly target
    - Today minutes
    - Week hours
  - entity: custom-plan
    effect: creates
    facts:
    - Name
    - Study goal
    - Focus length
    - Random range
    - Short break
    - Long break
    - Cadence
    - Planned blocks
  - entity: daily-goal
    effect: creates
    facts:
    - Date
    - Minutes
    - Subject allocations
    - Repeat through Sunday
    - Progress
    - Completed progress
  - entity: focus-session
    effect: creates
    facts:
    - Subject
    - Started at
    - Minutes
    - Label
    - Owner
  - entity: achievement
    effect: creates
    facts:
    - Name
    - Target
    - Progress
    - Earned at
    to: Earned
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

# Recover saved study data

## Trigger

A confirmed linked identity is restored.

## Outcome

The Product merges completed sessions by identity, chooses the latest settings snapshot and retains the earliest known earned badge dates.
