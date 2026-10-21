---
appliesTo:
- type: entity
  id: study-group
- type: entity
  id: group-membership
references:
- kind: code
  role: implementation
  target: lib/core/services/study_group_service.dart#leave
- kind: code
  role: implementation
  target: firestore.rules
---

# Private groups contain at most thirty-two members

A group has 1–32 members and a whole-hour shared target from 1–1,000. Names contain 1–60 characters. Leaving removes that person’s row, transfers an owner’s responsibility to a remaining member, and removes the group and invite when no members remain.
