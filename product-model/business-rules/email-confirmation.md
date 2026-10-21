---
appliesTo:
- type: entity
  id: account
  facts:
  - Email
  - Email verified
- type: capability
  id: create-account
- type: capability
  id: verify-email
references:
- kind: code
  role: implementation
  target: lib/core/services/firebase_auth_service.dart#FirebaseAuthService
---

# Email accounts remain pending until mailbox confirmation

Email signup requires a password of at least eight characters and leads to verification. Normal linked use waits for email confirmation; resending verification has a sixty-second cooldown. The supported provider determines the identity-confirmation flow.
