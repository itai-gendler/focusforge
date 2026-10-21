---
appliesTo:
- type: entity
  id: focus-session
- type: entity
  id: focus-timer
references:
- kind: code
  role: implementation
  target: lib/core/providers/study_providers.dart#TimerNotifier
- kind: code
  role: implementation
  target: lib/core/providers/study_providers.dart#SessionsNotifier
---

# Recovery retains one completed block and one award

Repeated recovery of the same completed block does not duplicate its history or XP. An elapsed block found at cold launch is credited once and leaves a fresh idle focus block; missed time does not invent a chain of completed phases.
