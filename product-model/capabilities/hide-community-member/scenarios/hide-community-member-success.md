---
kind: primary
routes:
  app: Android app
steps:
- text: Choose Hide member from another person’s row.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::linked::groups
- text: The Product saves the hidden member choice and omits their rows locally.
  kind: product
  entities:
  - entity: account
    effect: changes
    facts:
    - Hidden members
  actor: learner
  contexts:
    app:
      place: android::linked::groups
references:
- kind: code
  role: implementation
  target: lib/shared/widgets/community_safety.dart#CommunityMemberMenu
- kind: code
  role: implementation
  target: lib/core/providers/community_providers.dart#BlockedCommunityUsers
---

# Hide community member

## Trigger

Choose Hide member from another person’s row.

## Outcome

The Product saves the hidden member choice and omits their rows locally.
