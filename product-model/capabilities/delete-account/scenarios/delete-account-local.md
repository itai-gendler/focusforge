---
kind: alternate
routes:
  local: Local study
steps:
- text: Confirm deletion of this local profile and progress.
  kind: actor
  entities: []
  actor: learner
  contexts:
    local:
      place: android::local::privacy
- text: The Product clears the local account and its completed study.
  kind: product
  entities:
  - entity: account
    effect: removes
    from: Local
  - entity: focus-session
    effect: removes
    with: account
  actor: learner
  contexts:
    local:
      place: android::local::privacy
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
---

# Delete local study data

## Trigger

A local-only learner confirms deletion.

## Outcome

The device’s local identity and study data are cleared and Welcome opens.
