---
appliesTo:
- type: entity
  id: study-group
  effect: changes
  facts:
  - Member count
  - Owner
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
references:
- kind: code
  role: implementation
  target: firestore.rules
- kind: code
  role: implementation
  target: lib/core/services/study_group_service.dart#FirebaseStudyGroupService
---

# Joining and departing members change their group membership

A learner adds or removes their own membership. An owner’s departure transfers ownership to a remaining member. Other group metadata is retained.
