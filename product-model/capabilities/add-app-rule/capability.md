---
availability:
- place: android::local
- place: android::linked
references:
- kind: code
  role: implementation
  target: lib/core/providers/shield_providers.dart#WhitelistNotifier
- kind: code
  role: implementation
  target: lib/features/shield/shield_screen.dart#ShieldScreen
- kind: code
  role: implementation
  target: lib/features/shield/shield_access.dart#ensureShieldAccess
domain: shield
---

# Add app rule

Choose a policy for one installed app in Shield.
