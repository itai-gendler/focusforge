---
appliesTo:
- type: context
  context:
    place: android::local
- type: context
  context:
    place: android::linked
references:
- kind: code
  role: implementation
  target: lib/core/localization/app_strings.dart#AppStrings
---

# The device language order selects the supported app language

The app follows the first supported language in the device’s ordered preferences and falls back to English. It has no saved in-app language choice. User-entered subject, plan and profile names remain user content.
