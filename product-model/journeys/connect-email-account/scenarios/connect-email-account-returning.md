---
kind: alternate
result: achieved
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
  capability: sign-in-account
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
  capability: sign-in-account
- text: Return after confirming the email and refresh verification.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::local::verification
  capability: verify-email
- text: The Product refreshes the credential and restores the linked profile.
  kind: product
  entities:
  - entity: account
    effect: changes
    facts:
    - Email verified
    - Backup status
    from: Verification pending
    to: Connected
  actor: learner
  contexts:
    app:
      place: android::local::verification
  capability: verify-email
references:
- kind: code
  role: implementation
  target: lib/core/services/firebase_auth_service.dart#_acceptEmailCredential
- kind: code
  role: implementation
  target: lib/app/router.dart#routerProvider
- kind: code
  role: implementation
  target: lib/shared/widgets/email_verification_panel.dart#EmailVerificationPanel
---

# Verify a pending returning email account

## Trigger

An email credential requires mailbox confirmation.

## Outcome

The learner follows the verification link, returns and has the linked profile accepted.
