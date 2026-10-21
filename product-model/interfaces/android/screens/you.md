---
entities:
- entity: account
  shows:
  - Display name
  - Persona
  - Avatar
  - XP
  - Level
  - Completed blocks
  - Focus hours
  - Current streak
  collects:
  - Display name
  - Persona
  - Avatar
- entity: subject
  shows:
  - Name
  - Appearance
  - Weekly target
  - Week hours
  collects:
  - Weekly target
- entity: preferences
  shows:
  - Appearance
  collects:
  - Appearance
references:
- kind: code
  role: implementation
  target: lib/features/profile/profile_screen.dart#ProfileScreen
---

# You

The learner’s profile, level, totals and streak, subject weekly targets and appearance.
