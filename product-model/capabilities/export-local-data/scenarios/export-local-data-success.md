---
kind: primary
routes:
  local: Local study
  linked: Linked account
steps:
- text: Choose Export all data (JSON), then Copy JSON.
  kind: actor
  entities: []
  actor: learner
  contexts:
    local:
      place: android::local::privacy
    linked:
      place: android::linked::privacy
- text: The Product copies the available local data to the clipboard.
  kind: product
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
  - entity: preferences
    effect: reads
    facts:
    - Appearance
    - Clock face
    - Ambient selection
    - Ambient volumes
    - Notification choices
    - Quiet hours
    - Hidden presets
  - entity: app-rule
    effect: reads
    facts:
    - App
    - Tier
    - Daily budget
    - Used today
  actor: learner
  contexts:
    local:
      place: android::local::privacy
    linked:
      place: android::linked::privacy
references:
- kind: code
  role: implementation
  target: lib/features/settings/privacy_screen.dart#PrivacyScreen
- kind: code
  role: implementation
  target: lib/core/services/local_store.dart#exportAll
---

# Export local data

## Trigger

Choose Export all data (JSON), then Copy JSON.

## Outcome

The Product copies the available local data to the clipboard.
