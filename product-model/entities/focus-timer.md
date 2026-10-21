---
references:
- kind: code
  role: implementation
  target: lib/core/providers/study_providers.dart#TimerState
- kind: code
  role: implementation
  target: lib/core/providers/study_providers.dart#TimerNotifier
domain: focus
---

# Focus timer

The current focus or break block, its chosen pace and the work in flight.

## Information kept

- **Plan** — Selected stock preset or custom plan.
- **Subject** — Selected subject, or unassigned.
- **Phase** — Focus, Short break or Long break.
- **Remaining time** — Time left in the current block.
- **Planned duration** — The current block length, including adjustments or one random sample.
- **Started at** — When the current focus block began.
- **Ends at** — Deadline while running.
- **Cycle position** — Number of focus phases traversed toward the long break.
- **Starting account** — The identity that started the current focus block.
- **Hidden duration** — Whether Random focus hides the block duration.

## States

### Ready

A fresh focus block waits to start.

### Running

Focus or break time is advancing.

### Paused

The current phase retains its remaining time.
