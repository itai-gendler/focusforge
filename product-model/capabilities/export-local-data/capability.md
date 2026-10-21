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
  target: lib/core/services/local_store.dart#exportAll
domain: account-privacy
---

# Export local data

Inspect and copy the device’s saved FocusForge data as JSON.
