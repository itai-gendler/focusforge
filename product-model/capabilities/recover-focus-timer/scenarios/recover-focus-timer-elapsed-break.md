---
kind: edge
routes:
  app: Android app
steps:
- text: A cold launch finds an elapsed break deadline.
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
  unattended: true
  contexts:
    app:
      place: android::focus
- text: The Product prepares an idle focus block and grants no study credit for the break.
  kind: product
  entities:
  - entity: focus-timer
    effect: changes
    facts:
    - Remaining time
    - Phase
    - Planned duration
    - Started at
    - Ends at
    from: Running
    to: Ready
  contexts:
    app:
      place: android::focus
references:
- kind: code
  role: implementation
  target: lib/core/providers/study_providers.dart:872-1003
- kind: code
  role: implementation
  target: lib/core/providers/study_providers.dart#TimerNotifier
---

# Recover an elapsed break

## Trigger

A cold launch finds an elapsed break deadline.

## Outcome

The Product prepares an idle focus block and grants no study credit for the break.
