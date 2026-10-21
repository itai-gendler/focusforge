---
references:
- kind: code
  role: implementation
  target: lib/core/providers/app_providers.dart#UserNotifier
- kind: code
  role: implementation
  target: lib/core/models/user.dart#GamificationStats
- kind: code
  role: implementation
  target: lib/core/services/firebase_auth_service.dart#FirebaseAuthService
domain: account-privacy
relations:
- entity: subject
  verb: owns
  cardinality: one-to-many
- entity: custom-plan
  verb: owns
  cardinality: one-to-many
- entity: focus-session
  verb: owns
  cardinality: one-to-many
- entity: achievement
  verb: owns
  cardinality: one-to-many
- entity: leaderboard-entry
  verb: owns
  cardinality: one-to-many
- entity: focus-timer
  verb: keeps
  cardinality: one-to-one
- entity: daily-goal
  verb: keeps
  cardinality: one-to-one
- entity: preferences
  verb: keeps
  cardinality: one-to-one
- entity: app-access
  verb: keeps
  cardinality: one-to-one
- entity: strict-mode
  verb: keeps
  cardinality: one-to-one
- entity: youtube-filters
  verb: keeps
  cardinality: one-to-one
- entity: app-rule
  verb: owns
  cardinality: one-to-many
---

# Account

The person’s profile, connection and study totals.

## Information kept

- **Display name** — The name used in greetings and chosen sharing.
- **Persona** — Student or Professional.
- **Focus intention** — Build a habit, Fewer distractions or Go deeper.
- **Avatar** — Initials, a chosen symbol or a profile photo.
- **Setup complete** — Whether first-run choices have been completed.
- **Email** — The address used for email sign-in or verification.
- **Email verified** — Whether an email credential has been confirmed.
- **Cloud available** — Whether this build has connected account services.
- **Backup status** — Local, pending, restoring or synced study data.
- **Leaderboard sharing** — Whether the person chose to publish weekly summaries.
- **XP** — Progress within the current level.
- **Level** — Current earned level, initially one.
- **Completed blocks** — The credited completed block count.
- **Focus hours** — Total credited study hours.
- **Current streak** — Consecutive local calendar days with completed study, allowing today to remain unfinished.
- **Hidden members** — Community people hidden on this account and device.

## States

### Local

Study identity without a linked credential.

### Verification pending

An email credential awaits mailbox verification.

### Connected

A linked credential is active.

### Signed out

A linked credential has been closed while local study data remains.

### Deleting

Confirmed account cleanup is in progress.
