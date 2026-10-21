---
kind: primary
routes:
  app: Android app
steps:
- text: Open the badge cabinet and inspect a badge.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::achievements
- text: The Product shows the badge target, measured progress and earned date when known.
  kind: product
  entities:
  - entity: achievement
    effect: reads
    facts:
    - Name
    - Target
    - Progress
    - Earned at
  actor: learner
  contexts:
    app:
      place: android::achievements
references:
- kind: code
  role: implementation
  target: lib/features/settings/achievements_screen.dart#AchievementsScreen
- kind: code
  role: implementation
  target: lib/core/providers/social_providers.dart#AchievementsNotifier
---

# View achievements

## Trigger

Open Achievements and inspect a badge.

## Outcome

The Product shows the badge target, measured progress and earned date when known.

## Edge cases

- Older earned badges may have an unknown unlock date.
- A later streak lapse does not relock an earned badge.
