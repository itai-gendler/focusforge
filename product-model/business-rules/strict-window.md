---
appliesTo:
- type: entity
  id: strict-mode
- type: entity
  id: app-rule
references:
- kind: code
  role: implementation
  target: android/app/src/main/kotlin/dev/focusforge/focusforge/shield/AppBlockingPolicy.kt#AppBlockingPolicy
- kind: code
  role: implementation
  target: android/app/src/main/kotlin/dev/focusforge/focusforge/shield/ShieldRules.kt#strictModeActive
---

# Strict Mode makes selected app rules full blocks during its window

While the confirmed commitment window is active, selected enforced app rules use full blocking instead of their ordinary budget or focus condition. The timed effect ends at its deadline.
