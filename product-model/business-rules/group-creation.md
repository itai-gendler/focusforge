---
appliesTo:
- type: entity
  id: study-group
  effect: creates
references:
- kind: code
  role: implementation
  target: firestore.rules
- kind: code
  role: implementation
  target: lib/core/services/study_group_service.dart#create
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
---

# Linked learners create private study groups

Creation is available to linked learners in a connected account build.
