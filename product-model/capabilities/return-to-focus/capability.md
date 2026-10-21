---
availability:
- place: android::local
- place: android::linked
references:
- kind: code
  role: implementation
  target: lib/features/shield/breath_gate.dart#BreathGateScreen
- kind: code
  role: implementation
  target: lib/core/providers/shield_providers.dart#BreathEventsNotifier
domain: shield
---

# Return to focus

Choose to leave the intercepted app and return to focusing.
