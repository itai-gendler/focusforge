---
appliesTo:
- type: entity
  id: group-membership
  effect: changes
  facts:
  - Role
permits:
- related:
  - verb: contains
    entity: study-group
  - verb: contains
    entity: group-membership
  - verb: holds
    entity: learner
  when:
  - entity: group-membership
    fact: Role
    is: Owner
references:
- kind: code
  role: implementation
  target: lib/core/services/study_group_service.dart#leave
- kind: code
  role: implementation
  target: firestore.rules
---

# A departing owner transfers the owner role to a remaining member

When the owner leaves a group that still has members, the first remaining member, the earliest to have joined, becomes its owner. Only the owner’s own departure hands the role on.
