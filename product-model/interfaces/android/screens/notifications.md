---
entities:
- entity: preferences
  shows:
  - Notification choices
  - Quiet hours
  collects:
  - Notification choices
  - Quiet hours
- entity: app-access
  shows:
  - Notifications
references:
- kind: code
  role: implementation
  target: lib/features/settings/notifications_screen.dart#NotificationsScreen
---

# Notifications

The notification categories, quiet hours and the running-timer countdown permission.
