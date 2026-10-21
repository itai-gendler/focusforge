---
kind: alternate
routes:
  app: Android app
steps:
- text: A supported Home or search feed is visible without ordinary video playback while the feed filter applies.
  kind: condition
  entities:
  - entity: youtube-filters
    effect: reads
    facts: &id001
    - Shorts
    - Home and search feed
    - Only while focusing
  unattended: true
  contexts:
    app:
      place: android::breathing
- text: The Product presents the feed pause flow.
  kind: product
  entities:
  - entity: youtube-filters
    effect: reads
    facts: *id001
  - entity: breath-encounter
    effect: creates
    facts:
    - App
    - Time
    - Decision
    - Owner
    - Exercise complete
    - Access until
    to: Offered
  contexts:
    app:
      place: android::breathing
references:
- kind: code
  role: implementation
  target: android/app/src/main/kotlin/dev/focusforge/focusforge/shield/YouTubeSurfaceSignals.kt#YouTubeSurfaceSignals
- kind: code
  role: implementation
  target: android/app/src/main/kotlin/dev/focusforge/focusforge/shield/FocusAccessibilityService.kt#FocusAccessibilityService
---

# Pause a supported feed

## Trigger

A supported Home or search feed is visible without ordinary video playback while the feed filter applies.

## Outcome

The Product presents the feed pause flow.
