---
kind: primary
routes:
  app: Android app
steps:
- text: Choose a weekly target from one to twenty hours and save.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::you
- text: The Product saves the target in half-hour increments and compares it with completed local-week hours.
  kind: product
  entities:
  - entity: subject
    effect: changes
    facts:
    - Weekly target
  actor: learner
  contexts:
    app:
      place: android::you
references:
- kind: code
  role: implementation
  target: lib/features/profile/widgets/subject_target_sheet.dart#showSubjectTargetSheet
- kind: code
  role: implementation
  target: lib/core/providers/study_providers.dart#setWeeklyTarget
---

# Edit subject weekly target

## Trigger

Choose a weekly target from one to twenty hours and save.

## Outcome

The Product saves the target in half-hour increments and compares it with completed local-week hours.
