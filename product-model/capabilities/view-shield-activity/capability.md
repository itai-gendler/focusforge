---
availability:
- place: android::local
- place: android::linked
references:
- kind: code
  role: implementation
  target: lib/features/shield/shield_screen.dart#_ActivityView
- kind: code
  role: implementation
  target: lib/core/providers/shield_providers.dart#BreathEventsNotifier
domain: shield
---

# View Shield activity

Review the local pause decisions, walk-away totals and twelve most recent encounters.
