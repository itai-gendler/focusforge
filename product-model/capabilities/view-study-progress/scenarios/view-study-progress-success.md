---
kind: primary
routes:
  app: Android app
steps:
- text: Choose a study range or a day to inspect.
  kind: actor
  entities: []
  actor: learner
  contexts:
    app:
      place: android::home
- text: The Product shows completed blocks, subject totals and the selected day’s goal progress.
  kind: product
  entities:
  - entity: focus-session
    effect: reads
    facts:
    - Subject
    - Started at
    - Minutes
    - Label
    - Owner
  - entity: subject
    effect: reads
    facts:
    - Name
    - Appearance
    - Weekly target
    - Today minutes
    - Week hours
  - entity: daily-goal
    effect: reads
    facts:
    - Date
    - Minutes
    - Subject allocations
    - Repeat through Sunday
    - Progress
  - entity: account
    effect: reads
    facts:
    - Current streak
  actor: learner
  contexts:
    app:
      place: android::home
references:
- kind: code
  role: implementation
  target: lib/core/providers/study_providers.dart#rangeBarsProvider
- kind: code
  role: implementation
  target: lib/core/providers/study_providers.dart#daySummaryProvider
- kind: code
  role: implementation
  target: lib/core/providers/goal_planner_providers.dart#activeFocusGoalSecondsProvider
- kind: code
  role: implementation
  target: lib/features/dashboard/dashboard_screen.dart#DashboardScreen
---

# View study progress

## Trigger

Choose a study range or a day to inspect.

## Outcome

The Product shows completed blocks, subject totals and the selected day’s goal progress.

## Edge cases

- An empty day is shown as no completed study, not invented activity.
- Removed subjects retain their recorded names in history.
- The current week is Monday-aligned; the month ends at today.
