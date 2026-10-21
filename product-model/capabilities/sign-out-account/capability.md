---
availability:
- place: android::linked
references:
- kind: code
  role: implementation
  target: lib/features/settings/privacy_screen.dart#PrivacyScreen
- kind: code
  role: implementation
  target: lib/core/services/firebase_auth_service.dart#signOut
domain: account-privacy
---

# Sign out of account

Close the linked credential while keeping local study and the cloud account.
