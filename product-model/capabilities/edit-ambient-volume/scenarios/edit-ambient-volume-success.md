---
kind: primary
routes:
  app: Android app
steps:
- text: Adjust a track’s volume.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::focus
- text: The Product saves and applies the volume between zero and full volume.
  kind: product
  entities:
  - entity: preferences
    effect: changes
    facts:
    - Ambient volumes
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

# Edit ambient volume

## Trigger

Adjust a track’s volume.

## Outcome

The Product saves and applies the volume between zero and full volume.
