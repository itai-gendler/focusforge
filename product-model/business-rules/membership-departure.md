---
appliesTo:
- type: entity
  id: group-membership
  effect: removes
references:
- kind: code
  role: implementation
  target: lib/core/services/study_group_service.dart#leave
- kind: code
  role: implementation
  target: firestore.rules
permits:
- related:
  - verb: holds
    entity: learner
  when:
  - entity: learner
    fact: Linked access
    is: true
  - entity: learner
    fact: Connected services
    is: true
---

# Members remove their own group memberships

A learner leaves using their own membership. Account deletion also removes that learner’s memberships.
