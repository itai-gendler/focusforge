---
appliesTo:
- type: entity
  id: focus-session
- type: entity
  id: focus-timer
- type: entity
  id: account
  facts:
  - XP
  - Completed blocks
  - Focus hours
references:
- kind: code
  role: implementation
  target: lib/core/providers/study_providers.dart#TimerNotifier
- kind: code
  role: implementation
  target: lib/core/providers/app_providers.dart#StatsNotifier
---

# Only completed focus blocks earn saved study credit

Finishing a focus block saves its actual planned whole minutes once and awards one XP per minute. Pausing, resetting or skipping unfinished focus grants no saved minutes or XP. Break time is never study credit.
