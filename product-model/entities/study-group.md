---
references:
- kind: code
  role: implementation
  target: lib/core/services/study_group_service.dart#FirebaseStudyGroupService
- kind: code
  role: implementation
  target: lib/features/settings/study_groups_screen.dart#StudyGroupsScreen
domain: study-groups
relations:
- entity: group-membership
  verb: contains
  cardinality: one-to-many
---

# Study group

A private group working toward a combined weekly study target.

## Information kept

- **Name** — Group name.
- **Weekly target** — Combined hours for everyone, from one to one thousand.
- **Invite code** — The ten-character code shared by members.
- **Owner** — The member responsible for the group.
- **Member count** — Current membership, up to thirty-two people.
- **Week** — Monday-to-Sunday UTC period.
- **Completed hours** — Sum of current-week member progress.
- **Focusing now** — Count of members with an active shared focus deadline.
