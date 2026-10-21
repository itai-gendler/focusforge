---
kind: alternate
routes:
  app: Android app
steps:
- text: A selected focus-only app is opened during a running focus phase.
  kind: condition
  entities:
  - entity: focus-timer
    effect: reads
    facts:
    - Plan
    - Subject
    - Phase
    - Remaining time
    - Planned duration
    - Started at
    - Ends at
    - Cycle position
    - Starting account
    - Hidden duration
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
- text: The Product presents the focus-session pause flow.
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

# Pause during a running focus phase

## Trigger

A selected focus-only app is opened during a running focus phase.

## Outcome

The Product presents the focus-session pause flow.
