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
domain: focus
---

# Pause focus timer

Pause a running focus or break phase while retaining remaining time.
