---
availability:
- place: android::local
- place: android::linked
references:
- kind: code
  role: implementation
  target: android/app/src/main/kotlin/dev/focusforge/focusforge/shield/YouTubeSurfaceSignals.kt#YouTubeSurfaceSignals
- kind: code
  role: implementation
  target: android/app/src/main/kotlin/dev/focusforge/focusforge/shield/FocusAccessibilityService.kt#FocusAccessibilityService
domain: shield
---

# Pause YouTube surface

Present the pause flow for a supported YouTube surface selected by the learner.
