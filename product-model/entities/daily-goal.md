---
references:
- kind: code
  role: implementation
  target: lib/core/models/focus_goal.dart#FocusGoalPlan
- kind: code
  role: implementation
  target: lib/core/providers/goal_planner_providers.dart#activeFocusGoalSecondsProvider
domain: home
---

# Daily goal

A target for one day, optionally repeated through that week’s Sunday.

## Information kept

- **Date** — The first local calendar day covered.
- **Minutes** — A positive daily target, up to twelve hours.
- **Subject allocations** — An optional exact split of the daily total.
- **Repeat through Sunday** — Whether subsequent days through Sunday reuse the target.
- **Progress** — Completed owned minutes plus the current owned focus block on the selected date.
- **Completed progress** — Owned completed minutes on the eligible day, used by launcher progress.
