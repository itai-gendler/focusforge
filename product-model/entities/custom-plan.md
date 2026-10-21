---
references:
- kind: code
  role: implementation
  target: lib/core/models/study.dart#CustomPlan
- kind: code
  role: implementation
  target: lib/core/providers/study_providers.dart#PlanLibraryNotifier
domain: focus
---

# Custom plan

A saved named pace with a study goal and fixed or random focus blocks.

## Information kept

- **Name** — The saved plan name.
- **Study goal** — Desired total focus minutes.
- **Focus length** — Fixed block minutes, or the midpoint used to derive random-plan breaks.
- **Random range** — Optional inclusive minimum and maximum focus minutes.
- **Short break** — Derived short break minutes.
- **Long break** — Derived long break minutes.
- **Cadence** — Focus phases before a long break.
- **Planned blocks** — The bounded number of blocks suggested by the study goal.
