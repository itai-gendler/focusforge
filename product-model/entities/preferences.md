---
references:
- kind: code
  role: implementation
  target: lib/core/providers/app_providers.dart#ThemeSettingsNotifier
- kind: code
  role: implementation
  target: lib/core/providers/audio_providers.dart#ActiveSoundsNotifier
- kind: code
  role: implementation
  target: lib/core/providers/social_providers.dart#NotificationsNotifier
---

# Preferences

The learner’s saved device choices for appearance, audio and notifications.

## Information kept

- **Appearance** — Device-following, Day or Dark mode, palette and AMOLED preference.
- **Clock face** — The selected focus clock face.
- **Ambient selection** — Selected looping tracks.
- **Ambient volumes** — Independent volume for each track.
- **Notification choices** — Saved choices for the eight notification categories.
- **Quiet hours** — Whether quiet hours are selected and their start and end hours.
- **Hidden presets** — Stock presets removed from the available list.
