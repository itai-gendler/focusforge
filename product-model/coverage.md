---
scope: The supported Android study, shielding, account, progress and community workflows at the pinned checkout.
method: Read-only static tracing from user interfaces through providers, native policy, persistence and account rules.
covered:
- description: Android app entry, setup and feature screens.
  paths:
  - lib/main.dart
  - lib/app/
  - lib/features/
  - lib/shared/widgets/
- description: Study, shielding, goals, account and community models and providers.
  paths:
  - lib/core/models/
  - lib/core/data/
  - lib/core/providers/
- description: Private study storage, account credentials, backup and connected group services.
  paths:
  - lib/core/services/
  - firestore.rules
- description: Android app-boundary policy, supported YouTube checks and widget presentation.
  paths:
  - android/app/src/main/kotlin/dev/focusforge/focusforge/
- description: Shipped language selection.
  paths:
  - lib/core/localization/
exclusions:
- description: Build tools, dependency forks and generators are implementation support.
  paths:
  - tool/
  - third_party/
  - android/build.gradle.kts
  - pubspec.yaml
- description: Test fixtures and marketing captures are evidence rather than a product contract.
  paths:
  - test/
  - android/app/src/test/
  - docs/screenshots/
  - docs/readme/
- description: Retired backend jobs and migration tools do not define an active operator interface.
  paths:
  - functions/
- description: Unreferenced legacy setup goal step and Home screen-time panels.
  paths:
  - lib/features/onboarding/goal_step.dart
  - lib/features/dashboard/widgets/screen_time_card.dart
  - lib/features/dashboard/widgets/app_distribution.dart
unmapped:
- description: Browser and iOS preview shells lack an independently established shipped contract.
  paths:
  - web/
  - ios/
- description: About, licences and external support links are peripheral to the core workflows.
  paths:
  - lib/features/settings/about_screen.dart
- description: Coaching overlays and replay controls are peripheral guidance.
  paths:
  - lib/features/onboarding/coach_marks.dart
  - lib/core/providers/coach_providers.dart
limitations: []
---

# Coverage
