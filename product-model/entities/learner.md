---
references:
- kind: code
  role: implementation
  target: lib/core/models/user.dart#Persona
relations:
- entity: account
  verb: uses
  cardinality: one-to-one
- entity: group-membership
  verb: holds
  cardinality: one-to-many
acts: external
kind: person
---

# Learner

A person studying or doing focused work, either locally or with a linked account. Student and Professional are profile preferences, not different privileges.

## Information kept

- **Linked access** — Whether this learner currently has a confirmed linked credential.
- **Connected services** — Whether the running build offers connected account services.
