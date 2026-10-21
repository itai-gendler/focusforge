---
entities:
- entity: account
  shows:
  - Display name
  - Backup status
  - Leaderboard sharing
- entity: focus-session
  shows:
  - Subject
  - Started at
  - Minutes
  - Label
  - Owner
- entity: subject
  shows:
  - Name
  - Appearance
  - Weekly target
  - Today minutes
  - Week hours
- entity: achievement
  shows:
  - Name
  - Target
  - Progress
  - Earned at
- entity: preferences
  shows:
  - Appearance
  - Clock face
  - Ambient selection
  - Ambient volumes
  - Notification choices
  - Quiet hours
  - Hidden presets
- entity: breath-encounter
  shows:
  - App
  - Time
  - Decision
references:
- kind: code
  role: implementation
  target: lib/features/settings/privacy_screen.dart#PrivacyScreen
---

# Account & privacy

A linked learner’s account controls: backup status, what is kept in the cloud, data export, clearing local analytics, signing out and deleting the account.
