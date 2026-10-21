---
availability:
- place: android::local
- place: android::linked
references:
- kind: code
  role: implementation
  target: android/app/src/main/kotlin/dev/focusforge/focusforge/shield/AppBlockingPolicy.kt#AppBlockingPolicy
- kind: code
  role: implementation
  target: android/app/src/main/kotlin/dev/focusforge/focusforge/shield/AppBlockingService.kt#AppBlockingService
domain: shield
---

# Pause selected app

Present the app pause flow when the selected app’s current policy applies.
