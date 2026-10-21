---
appliesTo:
- type: capability
  id: delete-account
- type: entity
  id: account
references:
- kind: code
  role: implementation
  target: lib/core/services/firebase_auth_service.dart#deleteAccount
- kind: code
  role: implementation
  target: lib/core/services/firestore_account_cleanup.dart#FirestoreAccountCleanup
---

# Linked account deletion completes cloud cleanup before removing the login

Confirmed ownership precedes linked account deletion. Pending writes must finish before cleanup. Cloud records are removed before the authentication account, and local progress is cleared after successful deletion. A failure preserves local history for retry even when some cloud cleanup already succeeded.
