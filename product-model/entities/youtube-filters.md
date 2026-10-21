---
references:
- kind: code
  role: implementation
  target: lib/core/models/shield.dart#YoutubeRules
- kind: code
  role: implementation
  target: android/app/src/main/kotlin/dev/focusforge/focusforge/shield/YouTubeSurfaceSignals.kt#YouTubeSurfaceSignals
domain: shield
---

# YouTube filters

Selected supported surfaces within YouTube, independent of a whole-app rule.

## Information kept

- **Shorts** — Whether supported Shorts playback is paused.
- **Home and search feed** — Whether supported feed surfaces are paused.
- **Only while focusing** — Whether filters apply only during a running focus phase.
