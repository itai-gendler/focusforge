---
availability:
- place: android::local
- place: android::linked
references:
- kind: code
  role: implementation
  target: lib/core/providers/social_providers.dart#NotificationsNotifier
- kind: code
  role: implementation
  target: lib/features/settings/notifications_screen.dart#NotificationsScreen
---

# Change notifications settings

Save notification category choices and quiet hours.
