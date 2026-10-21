---
kind: primary
routes:
  app: Android app
steps:
- text: Return after confirming the email and refresh verification.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::local::verification
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
references:
- kind: code
  role: implementation
  target: lib/core/services/firebase_auth_service.dart#refreshEmailVerification
- kind: code
  role: implementation
  target: lib/shared/widgets/email_verification_panel.dart#EmailVerificationPanel
---

# Confirm the email link

## Trigger

The learner has opened the verification email link.

## Outcome

The verified linked profile is recovered and setup or Home can continue.

## Edge cases

- An unconfirmed refresh leaves the verification screen open.
- Returning from the email or browser also refreshes verification.
