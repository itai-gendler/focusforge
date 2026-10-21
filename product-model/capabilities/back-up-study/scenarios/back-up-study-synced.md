---
kind: primary
routes:
  app: Linked account
steps:
- text: Connected study setup changes or a focus block completes.
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
- text: The Product privately saves the current setup and completed sessions, and unions earned badge dates.
  kind: product
  entities:
  - entity: account
    effect: changes
    facts:
    - Backup status
  - entity: subject
    effect: reads
    facts:
    - Name
    - Appearance
    - Weekly target
    - Today minutes
    - Week hours
  - entity: custom-plan
    effect: reads
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
    effect: reads
    facts:
    - Date
    - Minutes
    - Subject allocations
    - Repeat through Sunday
    - Progress
  - entity: focus-session
    effect: reads
    facts:
    - Subject
    - Started at
    - Minutes
    - Label
    - Owner
  - entity: achievement
    effect: reads
    facts:
    - Name
    - Target
    - Progress
    - Earned at
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

# Save private study changes

## Trigger

A connected learner changes study setup or completes a block.

## Outcome

The Product privately saves the current setup and completed sessions, and unions earned badge dates.
