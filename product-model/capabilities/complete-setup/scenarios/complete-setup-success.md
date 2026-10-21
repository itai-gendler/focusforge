---
kind: primary
routes:
  app: Android app
steps:
- text: Choose Open FocusForge after reviewing the saved choices.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::setup
- text: The Product marks setup complete and opens Home.
  kind: product
  entities:
  - entity: account
    effect: changes
    facts:
    - Setup complete
  actor: learner
  contexts:
    app:
      place: android::setup
references:
- kind: code
  role: implementation
  target: lib/features/onboarding/complete_step.dart#CompleteStep
- kind: code
  role: implementation
  target: lib/features/onboarding/onboarding_flow.dart#OnboardingFlow
---

# Complete setup

## Trigger

Choose Open FocusForge after reviewing the saved choices.

## Outcome

The Product marks setup complete and opens Home.

## Edge cases

- Leaving mid-setup preserves the account-scoped draft; returning resumes the saved stage.
- Usage Access is optional and does not prevent completing setup.
