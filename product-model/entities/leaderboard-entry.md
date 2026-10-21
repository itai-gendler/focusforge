---
references:
- kind: code
  role: implementation
  target: lib/core/services/leaderboard_service.dart#BoardRow
- kind: code
  role: implementation
  target: lib/core/providers/social_providers.dart#leaderboardPublisherProvider
domain: leaderboard
---

# Leaderboard entry

A learner’s opt-in summary for one local calendar week.

## Information kept

- **Name** — Shared display name.
- **Week** — Local week beginning Monday.
- **Minutes** — Completed owned focus minutes in that week.
- **Level** — Current earned level, when supplied.
- **Photo** — Optional profile thumbnail.
- **Rank** — Position among the returned weekly standings.
