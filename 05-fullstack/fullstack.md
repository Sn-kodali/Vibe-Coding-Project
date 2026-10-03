# Full-Stack: Data, Access Rules, Edge Cases, Deploy

> Module 5 · Full-Stack. Add data schemas, access rules, and edge cases; stress-test and deploy.

## Deployed link

_The working, shareable link that survives real users._

https://churn-driver-discovery.lovable.app

## Data schema

| Entity | Key fields | Notes |
|---|---|---|
| Seeded analytics data | cohort_key, driver_key, stage, KPI values, risk_score, quote, affected_pct | Includes cohorts, KPIs, funnel steps, churn drivers, risky users, and voice quotes. Read-only demo data for authenticated users. |
| User-owned workflow data | user_id, cohort_key, driver_key, status, plan fields, validation result, nudge draft | Includes intervention plans, intervention sessions, validation results, and nudge drafts. Persisted per user with RLS using auth.uid(). |

## Access rules

_Who can see / do what? Where are the auth boundaries?_

The app is behind an authentication boundary. Logged-out users are redirected to /auth. Users sign up or log in with email + password only. Google OAuth / SSO is not enabled, and email verification is disabled for prototype testing.

Shared seeded analytics data such as cohorts, KPIs, funnel steps, drivers, risky users, and voice quotes can be read by any authenticated user.

Private workflow data such as intervention plans, intervention sessions, validation results, and nudge drafts is scoped to the current authenticated user. Users can only read or write rows where user_id = auth.uid().

Retention nudges can be drafted, saved, approved, and previewed, but no real SendGrid email or external outreach is sent.

## Edge cases hardened

| Case | Before | After |
|---|---|---|
| Empty / first-run state | Empty or no-match states could feel broken or unclear. | Risky users table has empty states and recovery actions like clearing search or showing all drivers. |
| Bad / malicious input | Repeated clicks or out-of-order intervention steps could create confusing workflow states. | Pending flags block repeated writes, redundant clicks are no-ops, and intervention status moves sequentially. |
| Failure / offline | Offline or failed data loads could freeze the dashboard or create false success feedback. | App shows loading skeletons, dashboard error states, offline banner, disabled write actions while offline, and session-expiry handling. |

## Stress test results

_What you threw at it, and what held / broke._

Offline handling: supported
Repeated-click protection: supported
Out-of-order status handling: supported
Session expiry handling: supported
Driver focus across routes: supported
SendGrid disabled: supported
Seeded driver detection: supported
No workspace switching: supported
Client-derived kill-switch timing: supported
