---
availability:
- place: android::local
references:
- kind: code
  role: implementation
  target: lib/core/services/firebase_auth_service.dart#refreshEmailVerification
- kind: code
  role: implementation
  target: lib/shared/widgets/email_verification_panel.dart#EmailVerificationPanel
domain: account-privacy
---

# Verify email

Finish email ownership confirmation through the emailed link and refresh the app.
