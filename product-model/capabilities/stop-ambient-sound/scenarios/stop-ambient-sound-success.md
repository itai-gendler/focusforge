---
kind: primary
routes:
  app: Android app
steps:
- text: Turn off a selected track or choose Stop all.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::focus
- text: The Product stops the selected audio and saves the remaining selection.
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

# Stop ambient sound

## Trigger

Turn off a selected track or choose Stop all.

## Outcome

The Product stops the selected audio and saves the remaining selection.
