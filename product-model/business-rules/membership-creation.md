---
appliesTo:
- type: entity
  id: group-membership
  effect: creates
references:
- kind: code
  role: implementation
  target: lib/core/services/study_group_service.dart#join
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

# Linked learners create their own group memberships

Joining is performed by the linked learner for their own membership using the accepted group invite. Creation accompanying a newly created group follows that group’s creation permission.
