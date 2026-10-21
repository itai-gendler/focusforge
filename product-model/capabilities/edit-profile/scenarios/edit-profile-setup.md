---
kind: alternate
routes:
  app: Android app
steps:
- text: Choose a persona, focus intention and name.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::setup
- text: The Product saves the initial profile choices.
  kind: product
  entities:
  - entity: account
    effect: changes
    facts:
    - Display name
    - Persona
    - Focus intention
  actor: learner
  contexts:
    app:
      place: android::setup
references:
- kind: code
  role: implementation
  target: lib/features/profile/widgets/edit_profile_sheet.dart#showEditProfileSheet
- kind: code
  role: implementation
  target: lib/core/providers/app_providers.dart#UserNotifier
---

# Choose the first profile

## Trigger

First-run setup reaches the profile choices.

## Outcome

The saved persona, intention and name are ready for subject selection.
