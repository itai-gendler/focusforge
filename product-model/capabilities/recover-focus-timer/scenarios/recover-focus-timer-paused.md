---
kind: alternate
routes:
  app: Android app
steps:
- text: A cold launch finds a paused phase.
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
- text: The Product restores the same paused phase and remaining time.
  kind: product
  entities:
  - entity: focus-timer
    effect: changes
    facts:
    - Remaining time
    - Phase
    - Plan
    - Subject
    - Starting account
    from: Paused
    to: Paused
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

# Recover a paused block

## Trigger

A cold launch finds a paused phase.

## Outcome

The Product restores the same paused phase and remaining time.
