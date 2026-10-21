---
appliesTo:
- type: entity
  id: group-membership
  effect: changes
  facts:
  - Name
  - Week
  - Minutes
  - Focus until
references:
- kind: code
  role: implementation
  target: lib/core/services/study_group_service.dart#publish
- kind: code
  role: implementation
  target: firestore.rules
permits:
- related:
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

# Members publish their own group progress

Only the member’s own completed-progress summary is published. Scheduled refreshes continue the sharing accepted when joining.
