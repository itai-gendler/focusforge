---
appliesTo:
- type: entity
  id: app-rule
  facts:
  - Daily budget
  - Used today
- type: entity
  id: app-usage
references:
- kind: code
  role: implementation
  target: android/app/src/main/kotlin/dev/focusforge/focusforge/shield/AppBlockingPolicy.kt#DailyForegroundUsage
- kind: code
  role: implementation
  target: android/app/src/main/kotlin/dev/focusforge/focusforge/shield/AppBlockingService.kt#usedToday
---

# Daily budgets count foreground time since local midnight

The daily allowance uses foreground time clipped to the current local day, including a foreground interval spanning midnight. Reaching the allowance activates the budget rule.
