---
appliesTo:
- type: entity
  id: account
  facts:
  - XP
  - Level
references:
- kind: code
  role: implementation
  target: lib/core/models/user.dart#GamificationStats
---

# Each level consumes its increasing XP threshold

Level one requires 1,000 XP. Each subsequent level needs 250 more XP than the previous one. Crossing a threshold subtracts that level’s requirement and carries the remainder forward.
