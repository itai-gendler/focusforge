---
entities:
- entity: strict-mode
  shows:
  - Duration
  - Started at
  - Ends at
  - Phrase
  - Cooldown
  collects:
  - Duration
  - Phrase
references:
- kind: code
  role: implementation
  target: lib/features/settings/strict_mode_screen.dart#StrictModeScreen
---

# Strict Mode

The Strict Mode commitment: its lock length, whether it is active and when it ends, and the confirmation to start or end it.
