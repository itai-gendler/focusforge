---
kind: alternate
routes:
  app: Android app
steps:
- text: Submit the email credential.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::local::account-entry
- text: The Product opens Verify your email.
  kind: product
  entities:
  - entity: account
    effect: changes
    facts:
    - Email
    - Email verified
    from: Signed out
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

# Email still needs verification

## Trigger

An email credential succeeds but mailbox verification is pending.

## Outcome

The learner reaches Verify your email.
