# Engineering Handoff Note

> Module 4 · Production Specs. Open the black box, make the build legible to an engineer.

## What this is

_One paragraph an engineer can read in 60 seconds._

Churn Driver Discovery is an authenticated AI retention workspace for B2B SaaS teams. It helps Growth / Retention PMs diagnose first-90-day churn, review KPI and funnel evidence, inspect affected accounts, plan a PM-approved intervention, and prepare demo-safe retention nudges. The app is now a five-route Lovable-Cloud-backed workspace with persisted intervention state, RLS, and offline-aware writes.

## Architecture (plain language)

- **Frontend:** Frontend is built with React / TanStack-style file-based routing in Lovable. The app has a shared DashboardShell and five authenticated routes: Diagnose, Funnel Analysis, Affected Users, Intervention Plan, and Evidence Sources. Feature folders separate dashboard state, insight, KPIs, funnel, drivers, voice, risky users, intervention, and shared UI components.
- **Backend / data:** Backend uses Lovable Cloud / Supabase with email-password auth, seeded read-only analytics tables, and user-owned persisted workflow tables. Seeded data includes cohorts, KPIs, funnel steps, drivers, risky users, and voice quotes. User-owned data includes intervention sessions, validation results, intervention plans, and nudge drafts. RLS scopes private workflow data to auth.uid().
- **Key flows:** 1. User signs in and lands on Diagnose.
2. User reviews headline churn driver, KPIs, and ranked churn drivers.
3. User opens Funnel Analysis to inspect lifecycle drop-off and user quotes.
4. User opens Affected Users to review risky accounts and prepare a retention nudge.
5. User opens Intervention Plan to edit, save, approve, and review a PM-owned intervention.
6. User checks Evidence Sources to understand the simulated source context behind the retention signals.

## What's solid vs. what's duct tape

| Area | State | Notes |
|---|---|---|
| Auth, routing, and persisted workflow state | solid | Five authenticated routes, Supabase auth, RLS, persisted intervention state, validation results, and nudge drafts are working. |
| Driver detection and external integrations | rough | Churn drivers, risky users, connector cards, and SendGrid flow are still seeded/demo-safe. No real analytics pipeline, real connector ingestion, or real email sending is connected. |

## Risks & assumptions for the team

Engineers should not treat the churn drivers as computed yet; they are seeded recommendations, not live model outputs. Evidence Sources are simulated connector cards, not real integrations. SendGrid is demo-disabled and must stay server-side if implemented later. Kill-switch elapsed time is currently client-derived and should be computed server-side before it is trusted as a safety signal. Multi-tenancy is also deferred; the current workspace is effectively single-tenant.

## How to run it

```
Open the Lovable project or hosted preview URL. If running locally, install dependencies, start the dev server, and open the preview URL. The app starts at /auth when logged out and redirects to / after sign-in. Use the seeded demo data to test Diagnose → Funnel → Affected Users → Intervention Plan → Evidence Sources. Verify auth, route navigation, intervention persistence, offline states, and demo-disabled nudge behavior.
```
