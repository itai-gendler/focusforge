---
kind: primary
routes:
  app: Android app
steps:
- text: Choose plus five or minus five minutes.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::focus
- text: The Product changes this block’s length and, while running, its deadline by the same amount.
  kind: product
  entities:
  - entity: focus-timer
    effect: changes
    facts:
    - Planned duration
    - Ends at
    - Remaining time
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

# Adjust focus timer

## Trigger

Choose plus five or minus five minutes.

## Outcome

The Product changes this block’s length and, while running, its deadline by the same amount.

## Edge cases

- A change outside five to one hundred eighty minutes is not applied.
- Random focus hides the duration and does not offer duration adjustments.
- The next block uses its plan’s own length.
