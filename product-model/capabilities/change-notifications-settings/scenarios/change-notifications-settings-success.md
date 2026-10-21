---
kind: primary
routes:
  app: Android app
steps:
- text: Change notification choices or quiet hours.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::notifications
- text: The Product saves the preference values.
  kind: product
  entities:
  - entity: preferences
    effect: changes
    facts:
    - Notification choices
    - Quiet hours
  actor: learner
  contexts:
    app:
      place: android::notifications
references:
- kind: code
  role: implementation
  target: lib/core/providers/social_providers.dart#NotificationsNotifier
- kind: code
  role: implementation
  target: lib/features/settings/notifications_screen.dart#NotificationsScreen
---

# Change notifications settings

## Trigger

Change notification choices or quiet hours.

## Outcome

The Product saves the preference values.
