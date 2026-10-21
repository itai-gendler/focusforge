---
kind: primary
routes:
  app: Android app
steps:
- text: Read an installed FocusForge widget or the running timer notification.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::widgets
- text: The Product shows the relevant timer, daily target or completed weekly progress.
  kind: product
  entities:
  - entity: focus-timer
    effect: reads
    facts:
    - Subject
    - Phase
    - Remaining time
    - Hidden duration
  - entity: daily-goal
    effect: reads
    facts:
    - Minutes
    - Completed progress
  - entity: focus-session
    effect: reads
    facts:
    - Minutes
    - Started at
  actor: learner
  contexts:
    app:
      place: android::widgets
references:
- kind: code
  role: implementation
  target: android/app/src/main/kotlin/dev/focusforge/focusforge/widgets/FocusWidget.kt#FocusWidget
- kind: code
  role: implementation
  target: android/app/src/main/kotlin/dev/focusforge/focusforge/widgets/FocusLiveActivity.kt#FocusLiveActivity
- kind: code
  role: implementation
  target: android/app/src/main/kotlin/dev/focusforge/focusforge/widgets/WidgetSessionSummary.kt#WidgetSessionSummary
---

# View launcher progress

## Trigger

Read an installed FocusForge widget or the running timer notification.

## Outcome

The Product shows the relevant timer, daily target or completed weekly progress.

## Edge cases

- A Random focus block hides countdown and progress details that would reveal its sampled length.
- The daily-goal and weekly widgets open Home; the clock and study widgets open Focus.
- When the running timer ends, opening the app lets recovery reconcile the finished block.

## Displayed progress

Goal and weekly widgets use completed owned sessions; Home can additionally show the current block’s in-flight daily progress.
