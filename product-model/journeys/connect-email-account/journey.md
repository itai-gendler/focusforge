---
actors:
- learner
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

# Connect an email account

## Goal

Confirm the email credential and reach linked account use.

## Success criterion

Mailbox ownership is confirmed and the linked profile is accepted after recovery.
