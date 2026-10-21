---
availability:
- place: android::local
references:
- kind: code
  role: implementation
  target: lib/core/services/firebase_auth_service.dart#sendPasswordReset
- kind: code
  role: implementation
  target: lib/shared/widgets/email_auth_sheet.dart#EmailAuthSheet
domain: account-privacy
---

# Reset password

Request the provider’s password-reset email and follow its link to choose a replacement.
