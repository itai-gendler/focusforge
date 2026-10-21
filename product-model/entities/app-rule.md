---
references:
- kind: code
  role: implementation
  target: lib/core/models/shield.dart#WhitelistEntry
- kind: code
  role: implementation
  target: lib/core/providers/shield_providers.dart#WhitelistNotifier
domain: shield
---

# App rule

The learner’s chosen policy for an installed app.

## Information kept

- **App** — The selected installed app.
- **Tier** — Always allowed, Time budgeted, Blocked or Only while focusing.
- **Daily budget** — Daily allowance for Time budgeted apps.
- **Used today** — Measured foreground time today.
