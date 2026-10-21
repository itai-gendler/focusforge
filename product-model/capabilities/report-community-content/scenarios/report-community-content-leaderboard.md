---
kind: alternate
routes:
  app: Android app
steps:
- text: Enter the reason and continue from Report content.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::linked::leaderboard
- text: The Product opens the email draft using the displayed name.
  kind: product
  entities:
  - entity: leaderboard-entry
    effect: reads
    facts:
    - Name
  actor: learner
  contexts:
    app:
      place: android::linked::leaderboard
references:
- kind: code
  role: implementation
  target: lib/shared/widgets/community_safety.dart#reportCommunityContent
---

# Report a leaderboard row

## Trigger

A displayed weekly row is reported.

## Outcome

The external email draft contains the displayed person and reason for the learner to send.
