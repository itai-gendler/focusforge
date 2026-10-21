---
appliesTo:
- type: entity
  id: account
  facts:
  - Backup status
- type: entity
  id: focus-session
- type: capability
  id: recover-study
references:
- kind: code
  role: implementation
  target: lib/core/services/study_backup_service.dart#connect
---

# Recovery merges sessions and selects one latest settings snapshot

Recovery combines saved completed sessions by their stable identity. Settings are chosen as a whole snapshot by modification time, with the remote snapshot winning equal timestamps. First linking may carry the learner’s guest work into the linked identity. Switching registered accounts restores that account’s own saved study choices.
