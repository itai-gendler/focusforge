---
kind: primary
routes:
  app: Android app
steps:
- text: Confirm removal of the selected study area.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::focus
- text: The Product removes the subject, clears its timer selection and any daily allocation split, and retains the old name on completed records.
  kind: product
  entities:
  - entity: subject
    effect: removes
  - entity: focus-timer
    effect: changes
    facts:
    - Subject
  - entity: daily-goal
    effect: changes
    facts:
    - Subject allocations
  - entity: focus-session
    effect: changes
    facts:
    - Label
  actor: learner
  contexts:
    app:
      place: android::focus
references:
- kind: code
  role: implementation
  target: lib/core/providers/study_providers.dart#SubjectsNotifier
- kind: code
  role: implementation
  target: lib/features/focus/manage_subjects_sheet.dart#showManageSubjectsSheet
- kind: code
  role: implementation
  target: lib/core/models/subject_naming.dart#SubjectNaming
- kind: code
  role: implementation
  target: lib/core/providers/goal_planner_providers.dart#removeSubjectAllocation
---

# Remove subject

## Trigger

Confirm removal of a subject.

## Outcome

The Product removes the subject, clears its timer selection and any daily allocation split, and retains the old name on completed records.
