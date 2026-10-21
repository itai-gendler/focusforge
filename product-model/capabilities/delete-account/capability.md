---
availability:
- place: android::local
- place: android::linked
references:
- kind: code
  role: implementation
  target: lib/features/settings/privacy_screen.dart#PrivacyScreen
- kind: code
  role: implementation
  target: lib/core/services/firebase_auth_service.dart#deleteAccount
- kind: code
  role: implementation
  target: lib/core/services/firestore_account_cleanup.dart#FirestoreAccountCleanup
domain: account-privacy
---

# Delete account

Confirm account deletion, verify linked ownership, remove associated cloud records, then erase the local profile and progress.
