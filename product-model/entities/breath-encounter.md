---
references:
- kind: code
  role: implementation
  target: lib/features/shield/breath_gate.dart#BreathGateScreen
- kind: code
  role: implementation
  target: lib/core/providers/shield_providers.dart#BreathEventsNotifier
domain: shield
---

# Breath encounter

An encounter with the pause flow and the decision the person makes.

## Information kept

- **App** — The app that prompted the encounter.
- **Time** — When the decision occurred.
- **Decision** — Walked away or continued after breathing.
- **Owner** — The learner credited with the decision.
- **Exercise complete** — Whether the three breathing cycles have finished.
- **Access until** — End of a supported temporary access window.

## States

### Offered

The app pause flow offers a decision.

### Breathing

The three 4–7–8 cycles are in progress.

### Ready

The exercise is complete.

### Walked away

The learner returned to focus.

### Continued

The learner completed the offered continuation.
