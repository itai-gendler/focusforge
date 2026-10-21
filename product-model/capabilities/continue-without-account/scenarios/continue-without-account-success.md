---
kind: primary
routes:
  app: Android app
steps:
- text: Choose Skip for now.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::local::account-entry
- text: The Product retains existing local choices and opens setup or Home.
  kind: product
  entities:
  - entity: account
    effect: creates
    facts:
    - Display name
    - Persona
    - Focus intention
    - Avatar
    - Setup complete
    - Email
    - Email verified
    - Cloud available
    - Backup status
    - Leaderboard sharing
    - XP
    - Level
    - Completed blocks
    - Focus hours
    - Current streak
    - Hidden members
    to: Local
  actor: learner
  contexts:
    app:
      place: android::local::account-entry
references:
- kind: code
  role: implementation
  target: lib/core/services/firebase_auth_service.dart#FirebaseAuthService
- kind: code
  role: implementation
  target: lib/features/onboarding/auth_screen.dart#AuthScreen
---

# Continue without an account

## Trigger

Choose Skip for now on the account screen.

## Outcome

The Product retains existing local choices and opens setup or Home.
