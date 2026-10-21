---
appliesTo:
- type: entity
  id: custom-plan
- type: entity
  id: focus-timer
- type: entity
  id: group-membership
references:
- kind: code
  role: implementation
  target: lib/core/models/study.dart#PomodoroPreset
- kind: code
  role: implementation
  target: lib/core/providers/study_providers.dart#TimerNotifier
- kind: code
  role: implementation
  target: lib/core/providers/social_providers.dart#groupPublisherProvider
- kind: code
  role: implementation
  target: android/app/src/main/kotlin/dev/focusforge/focusforge/widgets/FocusLiveActivity.kt#FocusLiveActivity
---

# Random focus samples once and hides its duration

A random focus block samples inclusive whole minutes from its valid saved range. That sample is retained through pause and recovery. Focus displays, widgets and shared group presence do not disclose the sampled deadline. Completed minutes are recorded when the block finishes; breaks keep their ordinary visible duration.
