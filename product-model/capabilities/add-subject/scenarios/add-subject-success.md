---
kind: primary
routes:
  app: Android app
steps:
- text: Enter a distinct name and choose Add.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::focus
- text: The Product saves the new subject and selects it for the timer.
  kind: product
  entities:
  - entity: subject
    effect: creates
    facts:
    - Name
    - Appearance
    - Weekly target
    - Today minutes
    - Week hours
  - entity: focus-timer
    effect: changes
    facts:
    - Subject
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
---

# Add subject

## Trigger

Enter a distinct subject name and choose Add.

## Outcome

The Product saves the new subject and selects it for the timer.

## Edge cases

- Empty, duplicate and too-similar names remain editable with a specific explanation.
- Names in non-Latin scripts are supported.
