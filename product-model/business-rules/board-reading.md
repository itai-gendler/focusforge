---
appliesTo:
- type: entity
  id: leaderboard-entry
  effect: reads
  contexts:
  - place: android::linked
permits:
- actors:
  - learner
  when:
  - entity: learner
    fact: Linked access
    is: true
  - entity: learner
    fact: Connected services
    is: true
references:
- kind: code
  role: implementation
  target: lib/core/providers/social_providers.dart#weekBoardProvider
- kind: code
  role: implementation
  target: firestore.rules
---

# Linked learners read the weekly leaderboard

A connected linked learner can read weekly standings without opting into publication.
