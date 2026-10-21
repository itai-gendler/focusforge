---
kind: primary
routes:
  app: Android app
steps:
- text: Save the desired YouTube filter choices.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::shield
- text: The Product saves the selected supported surfaces and focus-only condition.
  kind: product
  entities:
  - entity: youtube-filters
    effect: changes
    facts:
    - Shorts
    - Home and search feed
    - Only while focusing
  actor: learner
  contexts:
    app:
      place: android::shield
references:
- kind: code
  role: implementation
  target: lib/core/providers/shield_providers.dart#YoutubeRulesNotifier
- kind: code
  role: implementation
  target: lib/features/shield/shield_screen.dart#ShieldScreen
- kind: code
  role: implementation
  target: android/app/src/main/kotlin/dev/focusforge/focusforge/shield/YouTubeSurfaceSignals.kt#YouTubeSurfaceSignals
---

# Edit YouTube filters

## Trigger

Save the desired YouTube filter choices.

## Outcome

The Product saves the selected supported surfaces and focus-only condition.
