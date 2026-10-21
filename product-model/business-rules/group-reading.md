---
appliesTo:
- type: entity
  id: study-group
  effect: reads
references:
- kind: code
  role: implementation
  target: firestore.rules
- kind: code
  role: implementation
  target: lib/core/providers/social_providers.dart#groupMembersProvider
permits:
- related:
  - verb: contains
    entity: group-membership
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

# Group members read their private group

A group’s metadata, invite and aggregate progress are presented to its members.
