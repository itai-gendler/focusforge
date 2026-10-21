---
kind: primary
routes:
  app: Android app
steps:
- text: Completed study, subject targets or a walk-away changes badge progress.
  kind: condition
  entities:
  - entity: focus-session
    effect: reads
    facts:
    - Subject
    - Started at
    - Minutes
    - Label
    - Owner
  - entity: subject
    effect: reads
    facts:
    - Name
    - Appearance
    - Weekly target
    - Today minutes
    - Week hours
  - entity: breath-encounter
    effect: reads
    facts:
    - App
    - Time
    - Decision
    - Owner
    - Exercise complete
    - Access until
  unattended: true
  contexts:
    app:
      place: android::achievements
- text: The Product records the earned badge and its first known unlock date.
  kind: product
  entities:
  - entity: achievement
    effect: changes
    facts:
    - Progress
    - Earned at
    from: Locked
    to: Earned
  contexts:
    app:
      place: android::achievements
references:
- kind: code
  role: implementation
  target: lib/core/providers/social_providers.dart#AchievementsNotifier
- kind: code
  role: implementation
  target: lib/core/providers/social_providers.dart#_measure
- kind: code
  role: implementation
  target: lib/core/services/achievement_service.dart#mergeAchievementTimes
---

# Reach a badge target

## Trigger

Completed study, subject targets or a walk-away changes badge progress.

## Outcome

The Product records the earned badge and its first known unlock date.
