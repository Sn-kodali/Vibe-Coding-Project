# Living PRD

> Module 4 · Production Specs. Refactor for readability; extract a living PRD that stays true as the build evolves.

## Problem

_What user problem does this solve? Tie to the validated hypothesis._

Churn Driver Discovery is a single-page product analytics workspace that helps a B2B SaaS retention team answer one question fast:

"Why are new users churning in their first 90 days, and what is the single best intervention to test next?"

It surfaces the lifecycle funnel, ranks the top churn drivers, ties each driver to verbatim user quotes and at-risk accounts, and walks the reviewer through selecting, starting, and validating one intervention experiment.

It is not a CRM, renewal dashboard, or customer success inbox. The scope is first-90-day activation churn.

## Users & jobs

- **Primary user:** Growth / Retention PM Growth / Retention PM/ customer success manager or teams at a B2B SaaS company responsible for improving activation, onboarding, and early retention.
- **Job to be done:** When first-90-day churn is rising, I want to identify the leading churn driver, understand the evidence behind it, see which accounts are affected, and approve the next intervention to test, so I can act before more accounts drop off.

## Scope

- **In:** - Authenticated AI retention workspace for first-90-day churn
- Diagnose screen with headline insight, KPIs, ranked churn drivers, and AI Retention Analyst
- Funnel Analysis screen showing onboarding/activation drop-off and user quotes
- Affected Users screen showing risky accounts and retention nudge entry points
- Intervention Test screen for PM-reviewed intervention planning and approval
- Evidence Sources / Data Source screen showing simulated connector context
- Loading, empty, error, offline, and action feedback states
- Seeded backend data for cohorts, KPIs, funnel steps, drivers, risky users, quotes, intervention plans, validation results, and nudge drafts
- **Out (explicitly):** - Real production analytics pipeline
- Real connector ingestion from Segment, Amplitude, Zendesk, Salesforce, or HubSpot
- Real SendGrid email sending
- Real Slack, Jira, CRM, or ticketing automation
- Automated customer outreach
- Real machine-learning churn prediction
- Production-grade experimentation platform
- Billing, admin settings, or full team collaboration

## Requirements

| # | Requirement | Priority | Acceptance criteria |
|---|---|---|---|
| 1 | Diagnose the leading first-90-day churn driver | Must | User can see the top churn driver, supporting KPI evidence, funnel context, user quotes, and affected accounts in the retention workspace. |
| 2 | Plan and approve the next retention intervention | Should | User can review the recommended intervention, edit/save the plan, approve it, and preview a retention nudge without triggering any real external action. |

## Data & events

_What gets stored, what gets tracked._

The app uses seeded Lovable Cloud backend data for the core retention workspace and user-owned workflow state.

Stored / seeded data:
- cohorts
- KPIs
- funnel steps
- churn drivers
- driver cohort stats
- risky users/accounts
- user quotes
- intervention plan defaults

User-owned persisted data:
- intervention plans
- intervention status/history
- validation results
- nudge drafts
- future/demo-disabled nudge send attempts

Tracked interactions:
- sign in / sign up
- select churn driver
- view funnel evidence
- filter affected users
- open risky user detail
- edit/save/approve intervention plan
- draft/save/approve/preview retention nudge
- view Evidence Sources
- loading, empty, error, offline, and feedback states

Mocked / demo-only:
- real connector syncs
- real SendGrid sending
- real external outreach
- real machine-learning churn prediction
- production customer data ingestion

## Open questions

1. What exact product event defines “first value” or the week-one aha action?

2. Which churn driver should be prioritized first in production: setup friction, delayed first value, low team adoption, or unclear product value?

3. What real data sources are required for reliable driver detection?

4. How should account risk be calculated once real customer/account data is connected?

5. Should intervention approval stay PM-owned, or should Customer Success also approve outreach?

6. What threshold proves an intervention worked: activation lift, reduced time-to-first-value, lower driver share, or eventual 90-day churn reduction?

7. When should SendGrid move from demo-disabled to real sending?

8. How should the product avoid over-automation while still helping teams act faster?
