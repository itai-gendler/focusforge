---
kind: primary
routes:
  local: Local study
  linked: Linked account
steps:
- text: Confirm Clear analytics.
  kind: actor
  entities: []
  actor: learner
  contexts:
    local:
      place: android::local::privacy
    linked:
      place: android::linked::privacy
- text: The Product removes local completed study and encounter history, resets progress totals and discards pending completion credit.
  kind: product
  entities:
  - entity: focus-session
    effect: removes
  - entity: breath-encounter
    effect: removes
    from: Walked away
    as: walk-away
  - entity: account
    effect: changes
    facts:
    - XP
    - Level
    - Completed blocks
    - Focus hours
    - Current streak
  - entity: subject
    effect: changes
    facts:
    - Today minutes
    - Week hours
  - entity: breath-encounter
    as: continued
    effect: removes
    from: Continued
  actor: learner
  contexts:
    local:
      place: android::local::privacy
    linked:
      place: android::linked::privacy
references:
- kind: code
  role: implementation
  target: lib/features/settings/privacy_screen.dart#PrivacyScreen
---

# Clear local analytics

## Trigger

Confirm Clear analytics.

## Outcome

The Product removes local completed study and encounter history, resets progress totals and discards pending completion credit.

## Edge cases

- Cloud study history already saved can return during later account recovery.
- Subject targets and earned badges are retained.
