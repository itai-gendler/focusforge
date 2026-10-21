---
appliesTo:
- type: capability
  id: activate-strict-mode
- type: capability-scenario
  id: end-strict-mode-early
- type: entity
  id: strict-mode
references:
- kind: code
  role: implementation
  target: lib/features/settings/strict_mode_screen.dart#_StrictCommitmentSheetState
---

# Activation and early ending both require the complete confirmation

Starting Strict Mode and ending it early both require the commitment phrase, the configured cooldown and a final confirmation. The default wait is sixty seconds. Dismissal before final confirmation makes no activation change.
