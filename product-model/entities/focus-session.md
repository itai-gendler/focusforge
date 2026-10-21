---
references:
- kind: code
  role: implementation
  target: lib/core/models/study.dart#FocusSession
- kind: code
  role: implementation
  target: lib/core/providers/study_providers.dart#SessionsNotifier
domain: focus
---

# Focus session

A saved completed focus block used by study history and credit.

## Information kept

- **Subject** — The subject studied, or unassigned.
- **Started at** — The start instant used to assign calendar progress.
- **Minutes** — Whole completed focus minutes, including supported block adjustments.
- **Label** — Retained subject name when the subject is removed.
- **Owner** — The account credited with the block.
