---
kind: edge
routes:
  app: Android app
steps:
- text: An interrupted completion is still pending persistence.
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
- text: The Product retries saving the completed block; an already saved block retains one history record and one credit.
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

# Retry a completed block write

## Trigger

An interrupted completion is still pending persistence.

## Outcome

The Product retries saving the completed block; an already saved block retains one history record and one credit.
