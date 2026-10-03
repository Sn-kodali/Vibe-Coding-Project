# PROMPTS.md: Living Prompt Pack

> Module 3 · Prompt Chaining. Re-architect the build with prompt chains; capture the reusable ones here.

## How to use this pack

_Each prompt is a reusable step. Chain them: the output of one becomes the input to the next._

## Prompt chain: Churn Driver Discovery Prompt Chain

### Step 1: Add the missing flow states that make the prototype testable: validation result, intervention detail/history, and cohort/data switcher.
```
Build the next phase in a strict sequence:

1. Add a validation result state on the existing dashboard after the reviewer clicks “Mark tested.” This should summarize the selected churn driver, selected intervention, and whether the kill switch was testable within 3 minutes.

2. Add an intervention detail/history view or expanded panel for the selected intervention. It should show status history: Selected → Started → Tested, plus the supporting evidence and expected impact for that intervention.

3. Add a cohort/data switcher state surfaced from the existing header pill. The switcher should match the small “Cohort: Last 90 days” pill already in the header and explain that other cohorts are locked until a data source is connected.

Navigation & order:
First make “Mark tested” reveal the validation result state, then make the intervention card expandable into a detail/history view, then add the cohort/data switcher state.

Do not create unrelated pages.
Keep everything connected to the current single-page dashboard and the first-90-day churn workflow.
```

### Step 2: Add loading, empty, error, and feedback states so the prototype behaves more like a real product instead of a static mockup.
```
Apply the following logic constraints and tether all behavior strictly to these rules:

Loading:
Use skeleton cards while dashboard data loads. Show skeleton placeholders for KPI cards, the lifecycle funnel, risky users table, and intervention recommendation card. Keep the page structure visible so the dashboard does not feel broken.

Empty state:
No risky users match this filter. Try another churn driver or clear the search.

Error state:
Could not load churn data. Refresh the dashboard or return to the first-90-day cohort.

Status feedback:
After each intervention action, show visible confirmation:
- Selected intervention
- Test started
- Intervention marked as tested

Do not add new product features.
Do not redesign the whole app.
Do not change the core flow.
Only add behavior states that make the prototype feel more credible.
```

### Step 3: Audit the intervention recommendation card, then make one surgical polish pass without changing the rest of the prototype.
```
Refine the intervention recommendation card using the current product analytics visual reference.

The card should feel like a polished insight/action panel:
- clear hierarchy
- strong evidence
- obvious status buttons
- visible next step

Start by listing the 3 biggest gaps in the current intervention recommendation card:
1. clarity of selected churn driver
2. visibility of supporting evidence
3. feedback after clicking Select, Start test, or Mark tested

Then refine only that card so the reviewer can quickly understand the churn driver, choose the intervention, and see the status update.

Do not change:
- dashboard layout
- KPI cards
- funnel
- risky users table
- quotes
- mock data structure
- overall visual style

Only polish the intervention recommendation card and its click feedback.
```

## Reusable techniques learned

- _____
- _____

## What broke (and the fix)

_Where a single mega-prompt failed and chaining fixed it._

_____
# PROMPTS.md: Living Prompt Pack

> Module 3 · Prompt Chaining. Re-architect the build with prompt chains; capture the reusable ones here.

## How to use this pack

_Each prompt is a reusable step. Chain them: the output of one becomes the input to the next._

## Prompt chain: [name your flow]

### Step 1: [purpose]
```
[prompt text, with {{variables}} for the parts you swap]
```
**Expects in:** _____
**Produces out:** _____

### Step 2: [purpose]
```
[prompt text]
```
**Expects in:** _____
**Produces out:** _____

### Step 3: [purpose]
```
[prompt text]
```
**Expects in:** _____
**Produces out:** _____

## Reusable techniques learned

- _____
- _____

## What broke (and the fix)

_Where a single mega-prompt failed and chaining fixed it._

_____
