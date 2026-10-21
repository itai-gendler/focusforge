---
kind: primary
result: achieved
routes:
  app: Android app
steps:
- text: Choose and save the initial profile.
  kind: actor
  entities:
  - entity: account
    effect: changes
    facts:
    - Display name
    - Persona
    - Focus intention
  actor: learner
  contexts:
    app:
      place: android::setup
  capability: edit-profile
- text: Choose initial subjects.
  kind: actor
  entities:
  - entity: subject
    effect: creates
    facts:
    - Name
    - Appearance
    - Weekly target
    - Today minutes
    - Week hours
  actor: learner
  contexts:
    app:
      place: android::setup
  capability: add-subject
- text: Choose the starting pace.
  kind: actor
  entities:
  - entity: focus-timer
    effect: changes
    facts:
    - Plan
    - Remaining time
    - Planned duration
    from: Ready
    to: Ready
  actor: learner
  contexts:
    app:
      place: android::setup
  capability: select-pace
- text: Finish the saved setup choices.
  kind: actor
  entities:
  - entity: account
    effect: changes
    facts:
    - Setup complete
  actor: learner
  contexts:
    app:
      place: android::setup
  capability: complete-setup
- text: The Product opens Home.
  kind: product
  entities: []
  actor: learner
  contexts:
    app:
      place: android::home
  capability: complete-setup
- text: Read the initial study progress.
  kind: actor
  entities:
  - entity: daily-goal
    effect: reads
    facts:
    - Date
    - Minutes
    - Subject allocations
    - Repeat through Sunday
    - Progress
  - entity: focus-session
    effect: reads
    facts:
    - Subject
    - Started at
    - Minutes
    - Label
  actor: learner
  contexts:
    app:
      place: android::home
  capability: view-study-progress
references:
- kind: code
  role: implementation
  target: lib/features/onboarding/onboarding_flow.dart#OnboardingFlow
- kind: code
  role: implementation
  target: lib/features/onboarding/complete_step.dart#CompleteStep
---

# Saved setup reaches Home

## Trigger

An account choice has completed and the learner continues first-run setup.

## Outcome

Home is ready with the saved profile, subjects and starting pace. Optional Usage Access can be declined.
