---
appliesTo:
- type: entity
  id: group-membership
  effect: reads
references:
- kind: code
  role: implementation
  target: firestore.rules
permits:
- related:
  - verb: contains
    entity: study-group
  - verb: contains
    entity: group-membership
  - verb: holds
    entity: learner
  when:
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
  - *id001
  - *id002
---

# Group members read their group standings

Members can read other member summaries in their own group.
