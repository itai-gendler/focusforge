---
kind: alternate
routes:
  app: Android app
steps:
- text: Choose Google and finish the provider confirmation.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::local::account-entry
- text: The Product connects the chosen identity and recovers its saved study data.
  kind: product
  entities:
  - entity: account
    effect: changes
    facts:
    - Email
    - Backup status
    from: Local
    to: Connected
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
- kind: code
  role: implementation
  target: lib/features/profile/widgets/link_account_sheet.dart#showLinkAccountSheet
---

# Sign in with Google

## Trigger

Choose Google and complete its account selection.

## Outcome

The selected linked identity and recovered study data are active.

## Edge cases

- Cancelling Google leaves the current local choices intact.
- An unavailable provider displays its configuration or connection error.

## Entry from local study

The same credential process is offered by You and the Study groups and Leaderboard account prompts. A first link retains eligible guest study; a returning registered identity restores its own saved study.
