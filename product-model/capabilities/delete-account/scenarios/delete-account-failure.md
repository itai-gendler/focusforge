---
kind: edge
routes:
  linked: Linked account
steps:
- text: Confirm deletion and the identity check.
  kind: actor
  entities: []
  actor: learner
  contexts:
    linked:
      place: android::linked::privacy
- text: The Product begins confirmed cleanup.
  kind: product
  entities:
  - entity: account
    effect: changes
    facts: []
    from: Connected
    to: Deleting
  actor: learner
  contexts:
    linked:
      place: android::linked::privacy
- text: The cloud cleanup cannot finish, so the Product keeps the login and local history for a retry.
  kind: product
  entities:
  - entity: account
    effect: reads
    facts: []
  actor: learner
  contexts:
    linked:
      place: android::linked::privacy
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

# Retry incomplete account deletion

## Trigger

Confirmed cloud cleanup cannot finish.

## Outcome

Local history and the login remain available for retry; some cloud records may already be removed.
