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

A local learner’s data controls: export, clearing local analytics, deleting this device’s profile and the way into signing in.
