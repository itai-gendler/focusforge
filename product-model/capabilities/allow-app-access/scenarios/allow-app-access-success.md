---
kind: primary
routes:
  app: Android app
steps:
- text: Choose the required access and complete the Android setting.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::app-access
- text: The Product rechecks the device grant and reports the resulting status.
  kind: product
  entities:
  - entity: app-access
    effect: changes
    facts:
    - Usage access
    - Overlay access
    - Accessibility access
    - Notifications
    - App boundaries
  actor: learner
  contexts:
    app:
      place: android::app-access
references:
- kind: code
  role: implementation
  target: lib/core/services/permission_manager.dart#PermissionManager
- kind: code
  role: implementation
  target: lib/features/onboarding/permissions_step.dart#PermissionsStep
- kind: code
  role: implementation
  target: lib/features/dashboard/widgets/usage_access_card.dart
---

# Allow app access

## Trigger

Choose the required access and complete the Android setting.

## Outcome

The Product rechecks the device grant and reports the resulting status.

## Edge cases

- Declining access preserves local study functionality.
- Usage Access consent is also available during setup and on Home.
- YouTube Accessibility access has its own explanation and consent.
