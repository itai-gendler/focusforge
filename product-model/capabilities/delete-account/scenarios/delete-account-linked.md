---
kind: primary
routes:
  linked: Linked account
steps:
- text: Confirm deletion and complete the current provider’s ownership check.
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
- text: The Product removes the cloud records and the login, then clears this device’s profile, study data, app rules and memberships.
  kind: product
  entities:
  - entity: account
    effect: removes
    from: Deleting
  - entity: subject
    effect: removes
    with: account
  - entity: custom-plan
    effect: removes
    with: account
  - entity: focus-session
    effect: removes
    with: account
  - entity: achievement
    effect: removes
    from: Earned
    with: account
  - entity: leaderboard-entry
    effect: removes
    with: account
  - entity: focus-timer
    effect: removes
    with: account
    from: Ready
  - entity: daily-goal
    effect: removes
    with: account
  - entity: preferences
    effect: removes
    with: account
  - entity: app-rule
    effect: removes
    with: account
  - entity: group-membership
    effect: removes
  - entity: youtube-filters
    effect: removes
    with: account
  - entity: strict-mode
    effect: removes
    with: account
    from: 'Off'
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

# Delete a linked account

## Trigger

The learner confirms irreversible account deletion and fresh identity confirmation.

## Outcome

Cloud records and the login are removed; this device returns to Welcome with cleared progress.

## Edge cases

- Pending changes must finish syncing before cleanup begins.
- Long-running cleanup can ask for a fresh identity confirmation and one retry.
