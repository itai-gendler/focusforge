---
references:
- kind: code
  role: implementation
  target: lib/core/services/permission_manager.dart#PermissionManager
- kind: code
  role: implementation
  target: lib/core/providers/shield_providers.dart#appBlockingRunningProvider
---

# App access

Device grants and active app-boundary status reported back by Android.

## Information kept

- **Usage access** — Whether foreground app usage can be measured.
- **Overlay access** — Whether the pause screen can appear over selected apps.
- **Accessibility access** — Whether supported YouTube surfaces can be inspected.
- **Notifications** — Whether ongoing countdown notifications may be presented.
- **App boundaries** — Whether app-boundary monitoring is running or paused.
