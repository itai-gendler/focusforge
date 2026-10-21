---
appliesTo:
- type: entity
  id: subject
  facts:
  - Name
references:
- kind: code
  role: implementation
  target: lib/core/models/subject_naming.dart#SubjectNaming
---

# Subject names must be distinct within the catalogue

Creation rejects blank names, case-insensitive duplicates and names whose normalized identities collide with an existing subject or reserved setup suggestion. Non-Latin names receive stable identities.
