---
kind: alternate
routes:
  app: Android app
steps:
- text: Choose Resend after the displayed cooldown.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::local::verification
- text: The Product requests verification mail for the pending address.
  kind: product
  entities:
  - entity: account
    effect: reads
    facts:
    - Email
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

# Resend verification mail

## Trigger

The pending verification email is needed again.

## Outcome

A new verification message is requested and the resend cooldown begins.

## Edge cases

- Resend is available sixty seconds after the previous successful send.
- An unavailable email service shows an error and preserves the pending credential.
