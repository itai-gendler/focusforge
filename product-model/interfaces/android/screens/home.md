---
entities:
- entity: account
  shows:
  - Display name
  - Current streak
  - Level
- entity: daily-goal
  shows:
  - Date
  - Minutes
  - Subject allocations
  - Repeat through Sunday
  - Progress
  collects:
  - Minutes
  - Subject allocations
  - Repeat through Sunday
- entity: focus-session
  shows:
  - Subject
  - Started at
  - Minutes
  - Label
- entity: subject
  shows:
  - Name
  - Appearance
  - Today minutes
  - Week hours
- entity: focus-timer
  shows:
  - Phase
  - Remaining time
  - Subject
references:
- kind: code
  role: implementation
  target: lib/features/dashboard/dashboard_screen.dart#DashboardScreen
---

# Home

Today’s goal and its progress, the current streak, and completed study by day, week and month.
