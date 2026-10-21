---
kind: alternate
routes:
  app: Android app
steps:
- text: The running focus deadline reaches the plan’s long-break cadence.
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
- text: The Product banks the completed block once and starts the long break.
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
  - entity: subject
    effect: changes
    facts:
    - Today minutes
    - Week hours
  - entity: daily-goal
    effect: changes
    facts:
    - Progress
    - Completed progress
  - entity: focus-timer
    effect: changes
    facts:
    - Phase
    - Remaining time
    - Planned duration
    - Started at
    - Ends at
    - Cycle position
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
- kind: code
  role: implementation
  target: lib/core/providers/app_providers.dart#StatsNotifier
---

# Finish into a long break

## Trigger

The running focus deadline reaches the plan’s long-break cadence.

## Outcome

The Product banks the completed block once and starts the long break.
