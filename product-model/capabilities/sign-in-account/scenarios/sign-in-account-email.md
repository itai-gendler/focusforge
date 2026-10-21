---
kind: primary
routes:
  app: Android app
steps:
- text: Enter email and password.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::local::account-entry
- text: The Product connects the verified identity and begins private study recovery.
  kind: product
  entities:
  - entity: account
    effect: changes
    facts:
    - Email
    - Email verified
    - Backup status
    from: Signed out
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
---

# Sign in with verified email

## Trigger

Enter an existing email and password.

## Outcome

The verified account is connected after private study recovery.

## Edge cases

- Malformed email, incorrect credentials and provider errors show a retryable explanation.
- A new-device recovery failure retains the account entry flow until recovery can be retried.
