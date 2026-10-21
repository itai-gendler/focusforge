---
availability:
- place: android::local
- place: android::linked
references:
- kind: code
  role: implementation
  target: lib/core/providers/study_providers.dart#PlanLibraryNotifier
- kind: code
  role: implementation
  target: lib/core/models/study.dart#CustomPlan
- kind: code
  role: implementation
  target: lib/features/focus/custom_plan_sheet.dart#showCustomPlanSheet
- kind: code
  role: implementation
  target: lib/features/focus/focus_screen.dart#FocusScreen
domain: focus
---

# Remove pace

Remove a custom pace or hide a stock preset while retaining at least one usable pace. The selected pace’s unfinished block is reset after confirmation; removing another pace preserves it.
