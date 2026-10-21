---
kind: edge
routes:
  app: Android app
steps:
- text: A cold launch finds an elapsed running focus deadline.
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
- text: The Product saves that completed block and credits it once, then prepares a fresh idle focus block.
  kind: product
  entities:
  - entity: focus-session
    effect: creates
    facts:
    - Subject
    - Started at
    - Minutes
    - Label
    - Owner
  - entity: account
    effect: changes
    facts:
    - XP
    - Level
    - Completed blocks
    - Focus hours
    - Current streak
  - entity: focus-timer
    effect: changes
    facts:
    - Remaining time
    - Phase
    - Planned duration
    - Started at
    - Ends at
    - Cycle position
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

# Recover one elapsed focus block

## Trigger

A cold launch finds an elapsed running focus deadline.

## Outcome

The Product saves that completed block and credits it once, then prepares a fresh idle focus block.
