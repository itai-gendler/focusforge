---
appliesTo:
- type: entity
  id: study-group
  effect: removes
references:
- kind: code
  role: implementation
  target: firestore.rules
- kind: code
  role: implementation
  target: lib/core/services/study_group_service.dart#leave
permits:
- related:
  - verb: contains
    entity: group-membership
  - verb: holds
    entity: learner
  when:
  - fact: Member count
    is: 1
  - entity: learner
    fact: Linked access
    is: true
  - entity: learner
    fact: Connected services
    is: true
---

# The last member removes the empty group

Leaving as the final member removes the group and invite together.
