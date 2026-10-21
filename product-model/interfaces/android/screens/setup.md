---
entities:
- entity: account
  shows:
  - Display name
  - Persona
  - Focus intention
  - Setup complete
  collects:
  - Display name
  - Persona
  - Focus intention
- entity: subject
  shows:
  - Name
  - Appearance
  collects:
  - Name
- entity: focus-timer
  shows:
  - Plan
  collects:
  - Plan
- entity: custom-plan
  shows:
  - Name
  - Study goal
  - Focus length
  - Random range
  - Short break
  - Long break
  - Cadence
  - Planned blocks
  collects:
  - Name
  - Study goal
  - Focus length
  - Random range
- entity: app-access
  shows:
  - Usage access
references:
- kind: code
  role: implementation
  target: lib/features/onboarding/onboarding_flow.dart#OnboardingFlow
---

# Welcome

First-run setup: name, persona and focus intention, starting subjects, a starting pace and optional Usage Access.
