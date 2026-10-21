---
kind: primary
routes:
  app: Android app
steps:
- text: Choose the appearance settings.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::you
- text: The Product remembers the preferences and applies them to the app and supported widgets.
  kind: product
  entities:
  - entity: preferences
    effect: changes
    facts:
    - Appearance
  actor: learner
  contexts:
    app:
      place: android::you
references:
- kind: code
  role: implementation
  target: lib/core/providers/app_providers.dart#ThemeSettingsNotifier
- kind: code
  role: implementation
  target: lib/features/profile/profile_screen.dart#ProfileScreen
---

# Change appearance settings

## Trigger

Choose the appearance preferences.

## Outcome

The Product remembers the preferences and applies them to the app and supported widgets.
