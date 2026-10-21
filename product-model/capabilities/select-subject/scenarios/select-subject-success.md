---
kind: primary
routes:
  app: Android app
steps:
- text: Choose a study area, or clear the current selection.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::focus
- text: The Product uses the selected subject for the focus block.
  kind: product
  entities:
  - entity: focus-timer
    effect: changes
    facts:
    - Subject
  - entity: subject
    effect: reads
    facts:
    - Name
  actor: learner
  contexts:
    app:
      place: android::focus
references:
- kind: code
  role: implementation
  target: lib/features/focus/subject_picker.dart
- kind: code
  role: implementation
  target: lib/core/providers/study_providers.dart#setSubject
---

# Select subject

## Trigger

Choose a subject, or clear the current subject selection.

## Outcome

The Product uses the selected subject for the focus block.
