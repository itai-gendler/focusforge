---
kind: primary
routes:
  app: Android app
steps:
- text: A selected Blocked app becomes active while app boundaries are running.
  kind: condition
  entities:
  - entity: app-access
    effect: reads
    facts:
    - Usage access
    - Overlay access
    - Accessibility access
    - Notifications
    - App boundaries
  - entity: app-rule
    effect: reads
    facts:
    - App
    - Tier
    - Daily budget
    - Used today
  unattended: true
  contexts:
    app:
      place: android::breathing
- text: The Product presents the pause flow for the selected app.
  kind: product
  entities:
  - entity: app-rule
    effect: reads
    facts:
    - App
    - Tier
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

# Pause a blocked app

## Trigger

A selected Blocked app becomes active while app boundaries are running.

## Outcome

The Product presents the pause flow for the selected app.
