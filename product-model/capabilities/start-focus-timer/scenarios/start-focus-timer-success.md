---
kind: primary
routes:
  app: Android app
steps:
- text: Choose Start on the prepared block.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::focus
- text: The Product starts the focus deadline and remembers the starting identity.
  kind: product
  entities:
  - entity: focus-timer
    effect: changes
    facts:
    - Started at
    - Ends at
    - Remaining time
    - Starting account
    from: Ready
    to: Running
  actor: learner
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

# Start focus timer

## Trigger

Choose Start on the prepared block.

## Outcome

The Product starts the focus deadline and remembers the starting account.
