---
appliesTo:
- type: entity
  id: leaderboard-entry
  effect: changes
references:
- kind: code
  role: implementation
  target: lib/core/providers/social_providers.dart#leaderboardPublisherProvider
- kind: code
  role: implementation
  target: firestore.rules
permits:
- related:
  - verb: owns
    entity: account
  - verb: uses
    entity: learner
  when:
  - entity: account
    fact: Leaderboard sharing
    is: true
  - &id001
    entity: learner
    fact: Linked access
    is: true
  - &id002
    entity: learner
    fact: Connected services
    is: true
- unattended: true
  when:
  - entity: account
    fact: Leaderboard sharing
    is: true
  - *id001
  - *id002
---

# Opted-in account owners refresh their weekly entry

Only the owner’s own weekly summary is refreshed while sharing remains on.
