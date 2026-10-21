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
- kind: code
  role: implementation
  target: android/app/src/main/kotlin/dev/focusforge/focusforge/shield/ShieldRules.kt#strictModeActive
- kind: code
  role: implementation
  target: lib/core/providers/shield_providers.dart#strictModeActiveProvider
domain: strict-mode
---

# End Strict Mode

End the timed effect at its deadline, or end it early through the phrase, cooldown and final confirmation flow.
