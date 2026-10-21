---
appliesTo:
- type: entity
  id: custom-plan
- type: entity
  id: preferences
  facts:
  - Hidden presets
- type: entity
  id: focus-timer
references:
- kind: code
  role: implementation
  target: lib/core/providers/study_providers.dart#PlanLibraryNotifier
- kind: code
  role: implementation
  target: lib/core/providers/study_providers.dart#reconcilePresets
---

# At least one usable pace remains available

Removing custom or stock paces must leave one usable pace. Removing or changing the timing of the selected pace prepares a fresh focus block; changing another pace retains the current block.
