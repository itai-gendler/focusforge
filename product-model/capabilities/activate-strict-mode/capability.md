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

# Activate Strict Mode

Confirm the phrase, wait through the cooldown and confirm activation.
