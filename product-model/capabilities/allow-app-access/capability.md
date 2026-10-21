---
availability:
- place: android::local
- place: android::linked
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

Read the feature explanation, open the relevant Android permission control and recheck the resulting grant.
