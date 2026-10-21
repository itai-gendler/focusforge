---
kind: primary
routes:
  app: Android app
steps:
- text: Enter a nonempty display name and choose a persona.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::you
- text: The Product saves the personal profile choices.
  kind: product
  entities:
  - entity: account
    effect: changes
    facts:
    - Display name
    - Persona
  actor: learner
  contexts:
    app:
      place: android::you
references:
- kind: code
  role: implementation
  target: lib/features/profile/widgets/edit_profile_sheet.dart#showEditProfileSheet
- kind: code
  role: implementation
  target: lib/core/providers/app_providers.dart#UserNotifier
---

# Edit profile

## Trigger

Enter a nonempty display name and choose a persona.

## Outcome

The Product saves the personal profile choices.
