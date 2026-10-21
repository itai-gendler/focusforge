---
kind: alternate
routes:
  app: Android app
steps:
- text: Choose suggested study areas or add a custom name.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::setup
- text: The Product saves the selected subjects with their starting targets.
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
  actor: learner
  contexts:
    app:
      place: android::setup
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

# Choose initial subjects

## Trigger

Setup reaches the Subjects stage.

## Outcome

Selected suggestions and custom subjects form the initial catalogue.
