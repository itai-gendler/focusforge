---
entities:
- entity: app-rule
  shows:
  - App
  - Tier
  - Daily budget
  - Used today
  collects:
  - Tier
  - Daily budget
- entity: youtube-filters
  shows:
  - Shorts
  - Home and search feed
  - Only while focusing
  collects:
  - Shorts
  - Home and search feed
  - Only while focusing
- entity: app-access
  shows:
  - Usage access
  - Overlay access
  - Accessibility access
  - Notifications
  - App boundaries
- entity: breath-encounter
  shows:
  - App
  - Time
  - Decision
- entity: app-usage
  shows:
  - Day
  - App totals
references:
- kind: code
  role: implementation
  target: lib/features/shield/shield_screen.dart#ShieldScreen
---

# Shield

The learner’s app rules, YouTube filters and the access they need, with today’s app usage and recent pause decisions.
