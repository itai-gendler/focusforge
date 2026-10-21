---
appliesTo:
- type: entity
  id: app-rule
  effect: reads
permits:
- related:
  - verb: owns
    entity: account
  - verb: uses
    entity: learner
- unattended: true
  when:
  - entity: app-access
    fact: Usage access
    is: true
  - entity: app-access
    fact: Overlay access
    is: true
  - entity: app-access
    fact: App boundaries
    is: Running
references:
- kind: code
  role: implementation
  target: android/app/src/main/kotlin/dev/focusforge/focusforge/shield/AppBlockingPolicy.kt#AppBlockingPolicy
- kind: code
  role: implementation
  target: lib/features/shield/shield_access.dart#ensureShieldAccess
---

# App boundaries use the learner’s rules with the required device grants

The learner can inspect their selected rules. Automatic app-boundary evaluation requires Usage Access, overlay access and a running boundary service.
