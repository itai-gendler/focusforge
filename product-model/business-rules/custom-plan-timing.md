---
appliesTo:
- type: entity
  id: custom-plan
- type: entity
  id: focus-timer
references:
- kind: code
  role: implementation
  target: lib/core/models/study.dart#CustomPlan
- kind: code
  role: implementation
  target: lib/core/providers/study_providers.dart#TimerNotifier
---

# Custom plans derive breaks from the chosen focus length

A custom study goal spans 30–480 minutes and a focus length spans 10–120 minutes. Suggested blocks are the ceiling of goal divided by length, capped at 24. Short breaks are one fifth of the length rounded and bounded to 3–20 minutes; long breaks are 60 percent rounded and bounded to 10–45 minutes. Long-break cadence is 90 divided by length rounded and bounded to 2–6 focus phases. The timer continues its cycles until the learner changes it.
