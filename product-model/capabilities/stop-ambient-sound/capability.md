---
availability:
- place: android::local
- place: android::linked
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
domain: focus
---

# Stop ambient sound

Stop a selected loop, or stop all loops.
