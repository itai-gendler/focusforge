---
availability:
- place: android::local
- place: android::linked
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
domain: focus
---

# Complete timer phase

Advance an elapsed running focus or break phase. A completed focus phase banks its minutes once and starts the planned break; a completed break starts the next focus phase without study credit.
