---
references:
- kind: code
  role: implementation
  target: lib/core/models/shield.dart#StrictModeConfig
- kind: code
  role: implementation
  target: lib/features/settings/strict_mode_screen.dart#StrictModeScreen
domain: strict-mode
---

# Strict Mode

A timed personal commitment that makes selected app rules full blocks during its active window.

## Information kept

- **Duration** — Chosen window from fifteen minutes to eight hours.
- **Started at** — When activation was confirmed.
- **Ends at** — When the active window ends.
- **Phrase** — The commitment text required by the confirmation flow.
- **Cooldown** — Wait before final confirmation, sixty seconds by default.

## States

### Off

No active commitment window.

### Active

The confirmed commitment window is open.
