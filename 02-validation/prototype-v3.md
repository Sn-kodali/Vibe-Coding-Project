# Prototype (v3): The Build That Tests the Hypothesis

> Module 2 · Validation. The prototype is a hypothesis test, not a demo.

## Link

https://churn-driver-discovery.lovable.app

## What it tests

_Tie it back to the validation brief: which assumption does this prototype put in front of a user?_

This prototype tests whether Growth PMs and customer teams can move from a vague early-churn problem to a clear intervention decision: identify the leading churn driver, prioritize at-risk accounts, and choose the right intervention before users drop off in the first 90 days.

## Context injected (no placeholders)

- **Real user quotes on screen:** “I signed up, poked around for ten minutes, and never figured out what it actually did for my team.” / “Nobody on my team adopted it, so I stopped logging in. It felt like one more tool to babysit.” / “The value was probably in there somewhere, but I needed it to prove itself in week one, not month three.”
- **Domain metrics on screen:** 30% 90-day churn / 22% week-one activation rate / 1.4 seats active per account / 6.2 days median time-to-first-value / $1.1M ARR at risk

## Iteration log (v1 → v3)

| Version | Change | Why |
|---|---|---|
| v1 | Built a first-pass retention dashboard showing churn, activation, seats active, and time-to-first-value metrics. | To make the early-churn problem visible, but this version was too passive because users could see churn was happening without knowing why or what to do next. |
| v2 | Shifted from a dashboard to a churn diagnosis workflow with ranked churn drivers, supporting evidence, and account-level risk views. | To help users connect early activation issues to specific affected accounts instead of manually interpreting disconnected metrics. |
| v3 | Connected diagnosis to action by adding intervention approval, retention nudge draft/preview, evidence source context, and a SendGrid-ready nudge path. | To test whether users can identify delayed first value as the leading churn driver, prioritize accounts stalled before activation, and choose an intervention intended to improve week-one activation from 22% toward 40%. |
