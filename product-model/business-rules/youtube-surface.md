---
appliesTo:
- type: entity
  id: youtube-filters
references:
- kind: code
  role: implementation
  target: android/app/src/main/kotlin/dev/focusforge/focusforge/shield/YouTubeSurfaceSignals.kt#YouTubeSurfaceSignals
---

# YouTube filters distinguish playback from supported feed surfaces

The Shorts rule recognizes supported Shorts playback. The feed rule applies to supported Home and search feeds without ordinary video playback. The focus-only choice applies these filters during running focus blocks.
