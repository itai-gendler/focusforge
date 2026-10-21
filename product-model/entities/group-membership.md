---
references:
- kind: code
  role: implementation
  target: lib/core/models/social.dart#GroupMember
- kind: code
  role: implementation
  target: lib/core/services/study_group_service.dart#FirebaseStudyGroupService
domain: study-groups
---

# Group membership

One person’s membership and shared progress inside one private study group.

## Information kept

- **Name** — The member’s display name.
- **Role** — Owner or member within this group.
- **Joined at** — When this person joined.
- **Week** — UTC week represented by the shared minutes.
- **Minutes** — Completed focus minutes published for that week.
- **Focus until** — An optional active focus deadline.
- **Invite accepted** — The group invitation used to join.
