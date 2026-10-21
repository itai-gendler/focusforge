---
availability:
- place: android::local
- place: android::linked
references:
- kind: code
  role: implementation
  target: lib/features/settings/strict_mode_screen.dart#StrictModeScreen
- kind: code
  role: implementation
  target: lib/core/providers/shield_providers.dart#StrictModeNotifier
domain: strict-mode
---

# Edit Strict Mode duration

Choose the commitment window in fifteen-minute increments from fifteen minutes to eight hours.
