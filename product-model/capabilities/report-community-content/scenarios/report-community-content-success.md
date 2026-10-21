---
kind: primary
routes:
  app: Android app
steps:
- text: Enter a reason and choose Continue on Report content.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::linked::groups
- text: The Product opens an external email draft containing the displayed identity, group and reason.
  kind: product
  entities:
  - entity: group-membership
    effect: reads
    facts:
    - Name
  - entity: study-group
    effect: reads
    facts:
    - Name
  actor: learner
  contexts:
    app:
      place: android::linked::groups
references:
- kind: code
  role: implementation
  target: lib/shared/widgets/community_safety.dart#reportCommunityContent
---

# Report community content

## Trigger

Enter a reason and choose Continue on Report content.

## Outcome

The Product opens an external email draft containing the displayed identity, group and reason.

## Edge cases

- An empty reason does not open a draft.
- If an email app cannot open, the Product gives manual email instructions and explicitly says no report was sent.
