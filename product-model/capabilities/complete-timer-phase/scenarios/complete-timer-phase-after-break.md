---
kind: primary
routes:
  app: Android app
steps:
- text: The running break deadline is reached.
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
- text: The Product starts the next focus block without awarding study credit for break time.
  kind: product
  entities:
  - entity: focus-timer
    effect: changes
    facts:
    - Phase
    - Remaining time
    - Planned duration
    - Started at
    - Ends at
    - Starting account
    - Hidden duration
    from: Running
    to: Running
  contexts:
    app:
      place: android::focus
references:
- kind: code
  role: implementation
  target: lib/core/providers/study_providers.dart#TimerNotifier
- kind: code
  role: implementation
  target: lib/features/focus/focus_screen.dart#FocusScreen
---

# Return to focusing

## Trigger

The running break deadline is reached.

## Outcome

The Product starts the next focus block without awarding study credit for break time.
