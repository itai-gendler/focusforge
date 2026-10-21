---
kind: alternate
routes:
  app: Android app
steps:
- text: Choose Start with a Random focus plan selected.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::focus
- text: The Product uses one inclusive-range sample for this focus block and hides its duration.
  kind: product
  entities:
  - entity: focus-timer
    effect: changes
    facts:
    - Started at
    - Ends at
    - Remaining time
    - Starting account
    - Planned duration
    - Hidden duration
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

# Start a Random focus block

## Trigger

The selected plan has a random range.

## Outcome

One sampled duration runs without revealing its remaining time.
