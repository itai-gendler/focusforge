---
entities:
- entity: focus-timer
  shows:
  - Subject
  - Phase
  - Remaining time
  - Hidden duration
- entity: daily-goal
  shows:
  - Minutes
  - Completed progress
- entity: focus-session
  shows:
  - Minutes
  - Started at
- entity: preferences
  shows:
  - Appearance
references:
- kind: code
  role: implementation
  target: android/app/src/main/kotlin/dev/focusforge/focusforge/widgets/FocusWidget.kt#FocusWidget
---

# Launcher widgets and countdown

The Retro clock, Study session, Daily goal and Weekly progress widgets on the home screen, and the running timer’s countdown notification.
