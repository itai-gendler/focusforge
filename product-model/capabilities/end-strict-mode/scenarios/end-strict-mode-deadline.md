---
kind: primary
routes:
  app: Android app
steps:
- text: The saved commitment deadline is reached.
  kind: condition
  entities:
  - entity: strict-mode
    effect: reads
    facts:
    - Ends at
  unattended: true
  contexts:
    app:
      place: android::strict-mode
- text: The Product ends the active timed effect.
  kind: product
  entities:
  - entity: strict-mode
    effect: changes
    facts: []
    from: Active
    to: 'Off'
  contexts:
    app:
      place: android::strict-mode
references:
- kind: code
  role: implementation
  target: android/app/src/main/kotlin/dev/focusforge/focusforge/shield/ShieldRules.kt#strictModeActive
- kind: code
  role: implementation
  target: lib/core/providers/shield_providers.dart#strictModeActiveProvider
---

# Finish the commitment window

## Trigger

The saved commitment deadline is reached.

## Outcome

The Product ends the active timed effect.
