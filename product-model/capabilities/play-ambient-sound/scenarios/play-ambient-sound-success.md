---
kind: primary
routes:
  app: Android app
steps:
- text: Choose an inactive ambient track.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::focus
- text: The Product retains the selected track and starts it at its saved volume alongside other active tracks.
  kind: product
  entities:
  - entity: preferences
    effect: changes
    facts:
    - Ambient selection
  actor: learner
  contexts:
    app:
      place: android::focus
references:
- kind: code
  role: implementation
  target: lib/core/providers/audio_providers.dart#ActiveSoundsNotifier
- kind: code
  role: implementation
  target: lib/core/services/audio_service.dart#AmbientMixer
- kind: code
  role: implementation
  target: lib/features/focus/ambient_mixer.dart
---

# Play ambient sound

## Trigger

Choose an inactive ambient track.

## Outcome

The Product retains the selected track and starts it at its saved volume alongside other active tracks.

## Edge cases

- Playback failure preserves the selected mix and does not stop the focus timer.
- Launch restores the selection without automatically starting playback.
