---
availability:
- place: android::local
- place: android::linked
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
domain: you
---

# Edit avatar

Choose initials, a supplied symbol or a gallery photo for the profile.
