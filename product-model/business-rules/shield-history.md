---
appliesTo:
- type: entity
  id: breath-encounter
- type: capability
  id: return-to-focus
- type: capability
  id: continue-after-breathing
references:
- kind: code
  role: implementation
  target: lib/core/providers/shield_providers.dart#BreathEventsNotifier
- kind: code
  role: implementation
  target: lib/features/shield/breath_gate.dart#BreathGateScreen
---

# Shield history retains actual decisions in a bounded local window

The local encounter history contains actual pause decisions and retains at most the latest two hundred. An exercise preview adds no actual encounter. A single completed handoff is recorded once.
