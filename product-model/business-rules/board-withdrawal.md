---
appliesTo:
- type: entity
  id: leaderboard-entry
  effect: removes
references:
- kind: code
  role: implementation
  target: lib/core/services/leaderboard_service.dart#withdraw
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
  - entity: learner
    fact: Linked access
    is: true
  - entity: learner
    fact: Connected services
    is: true
---

# Account owners withdraw their own leaderboard entries

Withdrawal removes only the learner’s own published summaries, including during account deletion.
