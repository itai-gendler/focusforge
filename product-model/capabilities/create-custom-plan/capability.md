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
domain: focus
---

# Create custom plan

Save a named fixed or random focus pace from its study goal and block length.
