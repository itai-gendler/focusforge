---
kind: primary
routes:
  app: Android app
steps:
- text: Enter an email and a password of at least eight characters.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::local::account-entry
- text: The Product keeps the new credential pending, sends verification mail and opens Verify your email.
  kind: product
  entities:
  - entity: account
    effect: changes
    facts:
    - Email
    - Email verified
    from: Local
    to: Verification pending
  actor: learner
  contexts:
    app:
      place: android::local::verification
references:
- kind: code
  role: implementation
  target: lib/core/services/firebase_auth_service.dart#FirebaseAuthService
- kind: code
  role: implementation
  target: lib/features/onboarding/auth_screen.dart#AuthScreen
---

# Create an account

## Trigger

Enter an email and a password of at least eight characters.

## Outcome

The Product keeps the new credential pending, sends verification mail and opens Verify your email.

## Edge cases

- An existing email offers the sign-in path; invalid input remains editable.
- If verification mail cannot be sent, the pending credential remains available for resend.
