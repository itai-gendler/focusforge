---
appliesTo:
- type: entity
  id: youtube-filters
  effect: reads
permits:
- related:
  - verb: keeps
    entity: account
  - verb: uses
    entity: learner
- unattended: true
  when:
  - entity: app-access
    fact: Accessibility access
    is: true
references:
- kind: code
  role: implementation
  target: android/app/src/main/kotlin/dev/focusforge/focusforge/shield/FocusAccessibilityService.kt#FocusAccessibilityService
- kind: code
  role: implementation
  target: lib/features/shield/shield_access.dart#ensureShieldAccess
---

# YouTube filtering requires the learner’s Accessibility grant

The learner can inspect their selected filters. Automatic surface filtering requires the corresponding Android Accessibility access.
