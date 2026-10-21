---
availability:
- place: android::local
- place: android::linked
references:
- kind: code
  role: implementation
  target: lib/core/providers/shield_providers.dart#YoutubeRulesNotifier
- kind: code
  role: implementation
  target: lib/features/shield/shield_screen.dart#ShieldScreen
- kind: code
  role: implementation
  target: android/app/src/main/kotlin/dev/focusforge/focusforge/shield/YouTubeSurfaceSignals.kt#YouTubeSurfaceSignals
domain: shield
---

# Edit YouTube filters

Select Shorts and Home or search feed filtering, optionally only while focusing.
