---
entities:
- entity: focus-timer
  shows:
  - Plan
  - Subject
  - Phase
  - Remaining time
  - Planned duration
  - Cycle position
  - Hidden duration
  collects:
  - Subject
  - Plan
- entity: subject
  shows:
  - Name
  - Appearance
  - Weekly target
  - Today minutes
  - Week hours
  collects:
  - Name
  - Appearance
- entity: custom-plan
  shows:
  - Name
  - Study goal
  - Focus length
  - Random range
  - Short break
  - Long break
  - Cadence
  - Planned blocks
  collects:
  - Name
  - Study goal
  - Focus length
  - Random range
- entity: preferences
  shows:
  - Ambient selection
  - Ambient volumes
  - Clock face
  - Hidden presets
  collects:
  - Ambient selection
  - Ambient volumes
references:
- kind: code
  role: implementation
  target: lib/features/focus/focus_screen.dart#FocusScreen
---

# Focus

The timer: choose a pace and subject; start, pause, skip, adjust or reset a block; open the full-screen clock; and mix ambient sounds.
