---
kind: primary
routes:
  app: Android app
steps:
- text: Open Today on your list in Shield Activity.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::shield
- text: The Product presents listed apps with positive measured foreground minutes, busiest first.
  kind: product
  entities:
  - entity: app-usage
    effect: reads
    facts:
    - Day
    - App totals
  actor: learner
  contexts:
    app:
      place: android::shield
references:
- kind: code
  role: implementation
  target: lib/features/shield/shield_screen.dart#_ActivityView
---

# View app usage

## Trigger

Open today’s app usage information.

## Outcome

The Product presents listed apps with positive measured foreground time, busiest first.

## Edge cases

- Missing access is shown as unavailable measurement.
- A failed usage query does not remove saved study history.
