---
references:
- kind: code
  role: implementation
  target: lib/core/models/social.dart#Achievement
- kind: code
  role: implementation
  target: lib/core/providers/social_providers.dart#AchievementsNotifier
domain: achievements
---

# Achievement

An individual learner’s progress toward a shipped badge and its earned date.

## Information kept

- **Name** — The badge being pursued.
- **Target** — Required sessions, days, hours, walk-aways or weekly targets.
- **Progress** — Measured progress toward that target.
- **Earned at** — The earliest known unlock date; older awards may have an unknown date.

## States

### Locked

Progress remains below the target.

### Earned

The target was reached and the award is retained.
