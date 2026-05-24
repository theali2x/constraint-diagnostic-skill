# Constraint Diagnostic Skill

A public-safe AI-agent skill for diagnosing the single constraint blocking an outcome.

Preferred command:

`/constraint [situation]`

It works for:

- sales and business development
- client acquisition
- client diagnostics
- personal systems
- content loops
- AI agent workflows

The skill does not assume enough context. It first checks whether the supplied context is enough, then either diagnoses immediately or asks a minimal interview.

Output:

- CONSTRAINT
- WHY THIS ONE
- CONFIDENCE
- ASSUMPTIONS / MISSING CONTEXT
- NOT THE CONSTRAINT
- 7-DAY EXPERIMENT
- METRIC
- NEXT ACTION TODAY

## Usage

Paste or invoke:

```text
/constraint
Outcome:
Context:
Current chain:
Symptoms:
Numbers:
What I think it is:
Question:
```

You do not need to fill every field. The agent should ask only for missing context when needed.

## Files

- `SKILL.md` — the actual skill
- `README.md` — repo overview

## Safety note

This public version is generic by design. It does not include private workspace names, client details, credentials, personal operating-system references, or private examples.

## License

MIT. You can use, adapt, and share it.
