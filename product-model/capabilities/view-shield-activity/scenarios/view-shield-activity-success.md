---
kind: primary
routes:
  app: Android app
steps:
- text: Open the Shield overview.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::shield
- text: The Product shows the retained local decision history and walk-away totals.
  kind: product
  entities:
  - entity: breath-encounter
    effect: reads
    facts:
    - App
    - Time
    - Decision
  actor: learner
  contexts:
    app:
      place: android::shield
references:
- kind: code
  role: implementation
  target: lib/features/shield/shield_screen.dart#_ActivityView
- kind: code
  role: implementation
  target: lib/core/providers/shield_providers.dart#BreathEventsNotifier
---

# View Shield activity

## Trigger

Open the Shield overview.

## Outcome

The Product shows the retained local decision history and walk-away totals.
