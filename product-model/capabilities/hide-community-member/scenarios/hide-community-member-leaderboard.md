---
kind: alternate
routes:
  app: Android app
steps:
- text: Choose Hide member on the leaderboard row.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::linked::leaderboard
- text: The Product saves the local hidden-member choice.
  kind: product
  entities:
  - entity: account
    effect: changes
    facts:
    - Hidden members
  actor: learner
  contexts:
    app:
      place: android::linked::leaderboard
references:
- kind: code
  role: implementation
  target: lib/shared/widgets/community_safety.dart#CommunityMemberMenu
- kind: code
  role: implementation
  target: lib/core/providers/community_providers.dart#BlockedCommunityUsers
---

# Hide a leaderboard member

## Trigger

A leaderboard member should be hidden locally.

## Outcome

That person’s community rows no longer appear on this account and device.
