---
entities:
- entity: account
  shows:
  - Email
  - Backup status
  collects:
  - Email
references:
- kind: code
  role: implementation
  target: lib/features/onboarding/auth_screen.dart#AuthScreen
---

# Account

Where a learner signs in, creates an email account, resets a password or continues without an account.
