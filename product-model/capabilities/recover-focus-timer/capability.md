---
availability:
- place: android::local
- place: android::linked
references:
- kind: code
  role: implementation
  target: lib/core/providers/study_providers.dart:872-1003
- kind: code
  role: implementation
  target: lib/core/providers/study_providers.dart#TimerNotifier
domain: focus
---

# Recover focus timer

Recover a saved timer after suspension or a cold launch, preserving completed blocks without duplicate credit.
