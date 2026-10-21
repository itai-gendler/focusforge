---
appliesTo:
- type: entity
  id: account
  facts:
  - Current streak
- type: entity
  id: focus-session
references:
- kind: code
  role: implementation
  target: lib/core/providers/study_providers.dart#currentStreakProvider
---

# The current streak allows today to remain unfinished

The current streak counts consecutive local calendar days with at least one completed session. When today has none yet, yesterday may anchor the run; if neither day has a completion the streak is zero. Meeting a daily target is not required.
