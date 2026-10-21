---
kind: primary
routes:
  app: Android app
steps:
- text: Choose an avatar or a photo and save it.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::you
- text: The Product saves the avatar choice, making a bounded thumbnail for a selected photo.
  kind: product
  entities:
  - entity: account
    effect: changes
    facts:
    - Avatar
  actor: learner
  contexts:
    app:
      place: android::you
references:
- kind: code
  role: implementation
  target: lib/features/profile/widgets/avatar_sheet.dart#showAvatarSheet
- kind: code
  role: implementation
  target: lib/core/providers/app_providers.dart#UserNotifier
- kind: code
  role: implementation
  target: lib/core/services/profile_photo.dart#ProfilePhoto
---

# Edit avatar

## Trigger

Choose an avatar or a photo and save it.

## Outcome

The Product saves the avatar choice, making a bounded thumbnail for a selected photo.

## Edge cases

- Cancelling the photo picker retains the existing avatar.
- A photo-processing error offers another attempt.
