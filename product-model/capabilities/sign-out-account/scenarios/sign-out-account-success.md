---
kind: primary
routes:
  app: Linked account
steps:
- text: Confirm Sign out.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::linked::privacy
- text: The Product closes the credential, keeps saved local study and prepares an idle timer.
  kind: product
  entities:
  - entity: account
    effect: changes
    facts:
    - Backup status
    from: Connected
    to: Signed out
  - entity: focus-timer
    effect: changes
    facts:
    - Phase
    - Remaining time
    - Plan
    - Subject
    - Started at
    - Ends at
    from: Running
    to: Ready
  actor: learner
  contexts:
    app:
      place: android::linked::privacy
references:
- kind: code
  role: implementation
  target: lib/features/settings/privacy_screen.dart#PrivacyScreen
- kind: code
  role: implementation
  target: lib/core/services/firebase_auth_service.dart#signOut
---

# Sign out of account

## Trigger

Confirm Sign out.

## Outcome

The Product closes the credential, keeps saved local study and prepares an idle timer.

## Edge cases

- Published leaderboard rows remain until sharing is withdrawn or the account is deleted.
- Unsynced local study is retained for the next sign-in.
