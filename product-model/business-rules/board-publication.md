---
appliesTo:
- type: entity
  id: leaderboard-entry
  effect: creates
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

# Opted-in account owners publish their weekly entry

Publication is performed for the entry’s owner after positive completed weekly progress and consent. Automatic refresh uses the same consent.
