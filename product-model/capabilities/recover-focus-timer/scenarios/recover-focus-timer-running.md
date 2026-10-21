---
kind: primary
routes:
  app: Android app
steps:
- text: A cold launch finds a running block whose deadline remains ahead.
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
- text: The Product resumes the saved phase against its original deadline.
  kind: product
  entities:
  - entity: focus-timer
    effect: changes
    facts:
    - Remaining time
    - Ends at
    - Plan
    - Subject
    - Phase
    - Starting account
    from: Running
    to: Running
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

# Recover a future deadline

## Trigger

A cold launch finds a running block whose deadline remains ahead.

## Outcome

The Product resumes the saved phase against its original deadline.
