---
name: constraint
description: "Use when a user asks to find the one constraint or bottleneck in a business, client situation, personal system, content loop, sales process, or agent workflow. First check whether the supplied context is enough; if not, run a minimal interview. Then identify ONE constraint only and output a concise diagnostic card with confidence, assumptions, a 7-day experiment, one metric, and today's next action."
version: 1.0.0
author: Constraint Diagnostic Skill Contributors
license: MIT
metadata:
  hermes:
    tags: [constraint, bottleneck, diagnostics, operating-system, client-playbook]
    custom_command:
      category: Skill Commands
      label: constraint-diagnostic
      usage: /constraint [situation]
    aliases: [bottleneck, goldratt]
---

# Constraint Diagnostic

## Purpose

This skill turns vague stuckness into one clear constraint and one short experiment.

Use it when a user wants to understand what is actually blocking an outcome across:
- sales and business development
- client acquisition and delivery
- content and reputation building
- personal systems, energy, focus, or learning
- client businesses and consulting situations
- AI agent workflows, automations, and tool stacks

Core rule: identify ONE constraint only. Lists are allowed only as rejected alternatives or hypotheses before the final diagnosis.

## Command Interface

Preferred invocation:

`/constraint [situation]`

Useful aliases if configured:

`/bottleneck [situation]`

`/goldratt [situation]`

Good examples:

`/constraint outbound sales is stuck between sourcing and follow-up`

`/constraint client acquisition: I research tools but don't ship offers`

`/constraint this client has leads but sales are flat`

`/constraint my agent workflow for voice calls is brittle`

`/constraint my energy/focus has been inconsistent and I am not shipping`

## Context Template

The user may paste structured context. Do not require every field.

```
/constraint
Outcome:
Context:
Current chain:
Symptoms:
Numbers:
What I think it is:
Question:
```

Interpretation:
- Outcome: what result should improve.
- Context: relevant background.
- Current chain: input to output path.
- Symptoms: where it feels stuck.
- Numbers: counts, rates, time, dollars, frequency, delays.
- What I think it is: the user's current hypothesis.
- Question: the specific decision or diagnosis needed.

If the user provides enough context, diagnose. If not, ask the minimum number of questions needed.

## First Step: Context Sufficiency Check

Before diagnosing, classify the request into one of three states.

### A. Enough Context

Use when the prompt includes:
- a desired outcome
- a rough chain from input to outcome
- at least one symptom or stall point
- enough numbers or observations to make a bounded assumption

Say briefly:

`I have enough context to diagnose. I’ll state assumptions where needed.`

Then produce the diagnostic card.

### B. Almost Enough

Use when the situation is clear but 1-3 facts are missing.

Say:

`Almost enough. I need these missing facts before diagnosing:`

Ask only the missing questions. Prefer numbers.

Examples:
- `How many qualified prospects are sourced per day?`
- `How many outreaches are sent per day?`
- `What % of positive replies become calls?`
- `Where does work wait longest?`
- `What would improve if this constraint disappeared for 7 days?`

### C. Not Enough

Use when the prompt is too vague to avoid guessing.

Say:

`Not enough context yet. We need a short constraint interview.`

Then run the interview below. Do not dump all questions at once unless the user explicitly asks for a template.

## Minimal Interview

Ask one question at a time.

### Q1 — Outcome

Ask:

`What outcome are we optimizing for?`

Examples:
- `50 qualified outreaches/day`
- `more booked calls`
- `client revenue within 30 days`
- `consistent daily shipping`
- `voice agent reliably handling inbound calls`

If the goal is business, revenue or throughput is usually the target. If the goal is personal, ask for the observable metric: energy, consistency, hours shipped, sessions completed, sleep, etc.

### Q2 — Chain

Ask:

`Walk me through the chain from input to outcome.`

Examples:
- Outbound: `source prospects → qualify → message → follow up → call → close → activation`
- Client acquisition: `lead source → offer → outreach → call → proposal → close → delivery → case study`
- Content: `idea → post → profile visit → follow/DM → trust → opportunity`
- Client sales: `traffic → lead → booked call → show-up → close → onboarding → result`
- Personal system: `intention → environment → time block → start → sustain → finish → review`
- Agent workflow: `trigger → context retrieval → agent decision → tool/API → approval → output → logging → follow-up`

Look for missing steps. People skip the real constraint.

### Q3 — Pile-Up / Starvation

Ask:

`Where does work wait, stall, pile up, or depend on one person/tool? Where is the next step starved?`

Signals:
- unfinished conversations
- unreplied warm leads
- too much research, not enough sending
- booked calls but low show-up
- calls but no closes
- client work waiting on founder review
- agents producing drafts nobody reviews
- automations breaking at auth/API/tool steps
- many tasks started, few shipped

### Q4 — Lock-In Test

Ask:

`If that step had infinite capacity tomorrow and everything else stayed the same, would the target outcome move within 7-30 days? By how much?`

For longer-cycle businesses, allow 90 days. For operating loops, prefer 7-30 days.

If the answer is vague, the candidate is probably a symptom. Loop back to Q3.

## Domain Heuristics

Use these as hypotheses, not verdicts.

### Outbound Sales / Partnership Outreach

Common constraints:
- prospect sourcing quality
- qualification speed
- outbound volume
- offer/message clarity
- follow-up discipline
- reply-to-call conversion
- signup or onboarding friction
- activation after signup

False bottlenecks:
- `need more prospects` when warm replies are not followed up
- `need better tools` when daily outbound volume is low
- `need more research` when qualification is already good enough

### Client Acquisition

Common constraints:
- unclear packaged offer
- no narrow beachhead market
- not enough proof/demo assets
- outreach inconsistency
- call booking conversion
- proposal/close friction
- too many tools instead of one sellable workflow

False bottlenecks:
- `need a better stack` when no offer has been shipped
- `need more research` when the market has not been contacted
- `need a website` when the sales conversation is unclear

### Client Diagnosis

Common constraints:
- lead quality
- conversion step
- fulfillment capacity
- founder approval queue
- retention/churn
- unclear ownership
- no metric at each stage

Keep client-facing language professional. Do not mention unstated context or background assumptions unless the user explicitly provides them in the current context.

### Personal / Life Constraint

Common constraints:
- sleep/recovery
- environment design
- task selection
- unclear next action
- too many active commitments
- no feedback loop
- avoidance of one uncomfortable conversation/action

Do not force money language onto personal situations. Define the desired outcome first.

### Agent / Automation Constraint

Common constraints:
- missing trigger
- missing context retrieval
- brittle auth/API dependency
- no human approval gate
- no logging/receipt
- no next-action handoff
- too many tools without a stable workflow

For agent workflows, the experiment should test reliability, not vibes.

## Pushback Rules

Push back when the user or client names a fake bottleneck.

- `Need more leads` → check conversion and follow-up first.
- `Need to hire` → check whether the process is documented and delegatable.
- `Need better tools` → check whether the current process is being used consistently.
- `Need more time` → check priority, environment, and decision queues.
- `Need more capital` → check whether throughput is already proven.
- `Need a website/brand` → check whether offer and sales motion exist.
- `Need more content` → check offer, conversion, and distribution loop.
- `Need a more complex agent` → check trigger, context, approval, and logging.

Always use the user's numbers when available. If no numbers exist, mark the diagnosis as lower confidence and make the experiment generate the missing data.

## Diagnostic Card Format

Output this concise card. Keep it screenshot-friendly.

```
CONSTRAINT
[One sentence naming the single constraint.]

WHY THIS ONE
[2-4 bullets using the chain, pile-up, lock-in test, and any numbers.]

CONFIDENCE
[High / Medium / Low] — [one sentence why]

ASSUMPTIONS / MISSING CONTEXT
[State the assumptions. If none, write: None important.]

NOT THE CONSTRAINT
[The tempting false bottleneck and why it is downstream/upstream/noise. Skip if not relevant.]

7-DAY EXPERIMENT
[One cheap test. If we got this right, doing X for 7 days should move Y by Z.]

METRIC
[One number to track.]

NEXT ACTION TODAY
[One concrete action the user/client can do today.]
```

Do not add long theory after the card. If helpful, add one final line: `If this fails, rerun /constraint with the results.`

## Confidence Rules

High confidence:
- clear outcome
- clear chain
- visible pile-up/starvation
- lock-in test has numbers

Medium confidence:
- chain and symptoms are clear
- numbers are incomplete
- experiment can validate quickly

Low confidence:
- vague outcome
- no measured chain
- diagnosis is mainly a hypothesis

For low confidence, the 7-day experiment should instrument the chain, not fix it blindly.

## Client-Facing Mode

If the user says this is for a client or asks for client-safe output:
- remove user-specific references
- remove implementation-stack references unless they are part of the client's context
- use professional tone
- call it `PRIMARY CONSTRAINT` instead of `CONSTRAINT` if useful
- avoid blunt personal language unless explicitly requested

Client-facing card:

```
PRIMARY CONSTRAINT

EVIDENCE

IMPACT

WHAT IS NOT THE CONSTRAINT

7-DAY TEST

SUCCESS METRIC

RECOMMENDED NEXT STEP
```

## Examples

### Outbound Example

Input:

`/constraint Outcome: 50 qualified outreaches/day. Chain: source → qualify → message → follow-up → call → signup. Symptoms: I research too long and send too few messages. Numbers: 30 sourced/day, 8 messages/day, 2 replies/day. I think sourcing quality is the issue.`

Output style:

```
CONSTRAINT
Outbound send-throughput is the constraint, not sourcing quality.

WHY THIS ONE
- You already source ~30 prospects/day, but only send ~8 messages/day.
- The chain piles up between qualification and outreach.
- Improving sourcing quality cannot create 50 qualified outreaches/day while send volume stays at 8.

CONFIDENCE
High — the numbers show capacity exists upstream but does not convert into outreach volume.

ASSUMPTIONS / MISSING CONTEXT
Assuming the 30 sourced/day are at least roughly qualified.

NOT THE CONSTRAINT
Sourcing quality may matter later, but it is not the current throughput limiter.

7-DAY EXPERIMENT
For 7 days, cap research at 45 minutes and send 25 qualified messages before any extra sourcing. If this diagnosis is right, qualified outreaches/day should rise from 8 to 25+ without reply quality collapsing.

METRIC
Qualified outreaches sent per day and positive/neutral reply rate.

NEXT ACTION TODAY
Create today's 25-name send list and message all 25 before more research.
```

### Tool-Hoarding Example

```
CONSTRAINT
The constraint is offer shipment, not tool selection.

WHY THIS ONE
- Research is producing options, but no packaged offer is reaching prospects.
- More tools do not create market feedback.
- If offer shipment had infinite capacity, calls and objections would appear within 7-14 days.

CONFIDENCE
Medium — we need actual outreach numbers, but the behavior pattern is clear.

ASSUMPTIONS / MISSING CONTEXT
Assuming no active offer is currently being pitched daily.

NOT THE CONSTRAINT
The stack is not the constraint yet. It becomes relevant after one offer has repeated demand.

7-DAY EXPERIMENT
Ship one narrow offer to 20 qualified prospects in 7 days. If right, the metric should produce at least 3 positive/curious replies or clear objections.

METRIC
Qualified prospects contacted → positive/curious replies.

NEXT ACTION TODAY
Write the one-sentence offer and send it to 5 prospects.
```

### Client-Safe Example

```
PRIMARY CONSTRAINT
The main constraint is lead-to-call conversion.

EVIDENCE
Leads are entering the pipeline, but the next step is not consistently converting into booked calls. Increasing lead volume would mostly increase the number of unconverted leads.

IMPACT
Fixing this step should improve booked calls within 7-30 days without increasing ad spend.

WHAT IS NOT THE CONSTRAINT
Top-of-funnel lead volume is not the first constraint to address.

7-DAY TEST
For 7 days, every new qualified lead receives a response within 10 minutes plus two follow-ups within 72 hours.

SUCCESS METRIC
Qualified leads → booked calls percentage.

RECOMMENDED NEXT STEP
Create the response/follow-up template and run it on the next 20 qualified leads.
```

## Final Rule

Do not let the user leave with a list of priorities. The output must end with one constraint, one metric, and one next action.
