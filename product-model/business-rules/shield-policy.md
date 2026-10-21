---
appliesTo:
- type: entity
  id: app-rule
- type: entity
  id: app-access
references:
- kind: code
  role: implementation
  target: android/app/src/main/kotlin/dev/focusforge/focusforge/shield/AppBlockingPolicy.kt#AppBlockingPolicy
- kind: code
  role: implementation
  target: lib/features/shield/shield_access.dart#ensureShieldAccess
---

# An app rule applies according to its selected tier

Blocked pauses the selected app; Time budgeted pauses it once today’s foreground allowance is spent; Only while focusing applies during a running focus phase. Always allowed is the unrestricted tier. App boundaries require the corresponding Android device access.
