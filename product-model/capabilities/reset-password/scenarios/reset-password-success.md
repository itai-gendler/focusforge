---
kind: primary
routes:
  app: Android app
steps:
- text: Enter the sign-in email and request a password reset.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::local::account-entry
- text: The Product requests the reset email; the learner can finish the password change in the provider flow.
  kind: product
  entities:
  - entity: account
    effect: reads
    facts:
    - Email
  actor: learner
  contexts:
    app:
      place: android::local::account-entry
references:
- kind: code
  role: implementation
  target: lib/core/services/firebase_auth_service.dart#sendPasswordReset
- kind: code
  role: implementation
  target: lib/shared/widgets/email_auth_sheet.dart#EmailAuthSheet
---

# Reset password

## Trigger

Enter the account email and request a password reset.

## Outcome

The Product requests the reset email; the learner can finish the password change in the provider flow.

## Edge cases

- Invalid addresses stay in the form; connection or sending errors can be retried.
