---
availability:
- place: android::local
- place: android::linked
references:
- kind: code
  role: implementation
  target: android/app/src/main/kotlin/dev/focusforge/focusforge/shield/AppBlockingService.kt#showOverlay
- kind: code
  role: implementation
  target: lib/features/shield/breath_gate.dart#BreathGateScreen
domain: shield
---

# Complete breathing

Follow the guided exercise from an intercepted app or its Shield preview: three cycles of four-second inhale, seven-second hold and eight-second exhale. The completed exercise presents the decision.
