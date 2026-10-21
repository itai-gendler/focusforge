---
kind: alternate
routes:
  app: Android app
steps:
- text: The measured foreground time reaches the selected daily allowance.
  kind: condition
  entities:
  - entity: app-rule
    effect: reads
    facts: &id001
    - App
    - Tier
    - Daily budget
    - Used today
  unattended: true
  contexts:
    app:
      place: android::breathing
- text: The Product presents the pause flow with the used daily allowance.
  kind: product
  entities:
  - entity: app-rule
    effect: reads
    facts: *id001
  - entity: breath-encounter
    effect: creates
    facts:
    - App
    - Time
    - Decision
    - Owner
    - Exercise complete
    - Access until
    to: Offered
  contexts:
    app:
      place: android::breathing
references:
- kind: code
  role: implementation
  target: android/app/src/main/kotlin/dev/focusforge/focusforge/shield/AppBlockingPolicy.kt#AppBlockingPolicy
- kind: code
  role: implementation
  target: android/app/src/main/kotlin/dev/focusforge/focusforge/shield/AppBlockingService.kt#AppBlockingService
---

# Pause after today’s budget

## Trigger

The measured foreground time reaches the selected daily allowance.

## Outcome

The Product presents the pause flow with the used daily allowance.
