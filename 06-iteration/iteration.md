# Iteration: Analytics, Sprint, Final Recommendation

> Module 6 · Evals & Iteration. Read the analytics, run an iteration sprint, present with evidence.

## What the evidence says

_What real usage showed: numbers if your tool has analytics, counted behaviour if it does not. Put the signal that matters on screen._

- **Primary signal:** The primary signal is high bounce: 5 visitors reached the product, but the bounce rate was 100%, with only 1 view per visit. This means users reached the AI Retention Dashboard but did not meaningfully continue into the deeper workflow.
- **What moved:** The product got initial reach. Five people reached the live product, and the average session duration was 1m 25s, which suggests users spent some time reading or orienting on the first screen.
- **What didn't:** Depth did not move. Views per visit stayed at 1 and bounce rate was 100%, which means users were not continuing from the first screen into Funnel Analysis, Affected Users, Intervention Plan, or Evidence Sources.

_Analytics snapshot: visitors 5; page views 7; views per visit 1; duration 1 m 25 s; bounce 100._

## Iteration sprint

| Change | Hypothesis | Result |
|---|---|---|
| Added a clearer first-screen action path on Diagnose: a prominent “Start retention review” CTA and a 3-step workflow strip. | If users see a clearer next step on the Diagnose screen, more of them will continue into the core workflow instead of bouncing after one view. | Redeployed for the next test cycle. Success will be measured by lower bounce rate and higher views per visit. |

## The recommendation

**Decision:** ☐ Go  ☑ Iterate  ☐ Kill

_The evidence that justifies the call:_

Analytics showed 5 visitors, 7 page views, 1 view per visit, 1m 25s average duration, and 100% bounce rate. This means users reached the product, but they did not continue past the first screen. The product has enough initial interest to keep going, but the onboarding path from Diagnose into Affected Users and Intervention Plan needs to be clearer.

## Final showcase

- **Demo link:** https://churn-driver-discovery.lovable.app
- **The one-sentence story:** Churn Driver Discovery is an AI retention dashboard that helps Growth PMs diagnose first-90-day churn, review affected accounts, and choose the next intervention to test.
- **Where it landed on the Confidence Line (M2 → now):** Value risk is partly validated because users reached the product, but activation risk remains open because users did not continue past the first screen. The next confidence step is proving that a clearer CTA can move users from Diagnose into the intervention workflow.
