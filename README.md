# Teaching Deck Review

A Hermes Agent skill for reviewing and improving near-finished teaching decks with evidence.

It is designed for a review-first workflow:

```text
inspect → score baseline → preserve what works → prioritize P0/P1/P2
→ approve targeted fixes → revise a copy → rescore → verify → rehearse
```

## Install for Hermes

Copy or unzip this repository into the active Hermes skill directory:

```text
$HERMES_HOME/skills/productivity/teaching-deck-review/
```

If `HERMES_HOME` is not set, the usual path is:

```text
~/.hermes/skills/productivity/teaching-deck-review/
```

The folder must contain:

```text
SKILL.md
references/rubric.md
references/teaching-style.md
references/activity-design.md
references/review-report-template.md
```

Start a new Hermes session after installation so the skill loader sees it.

## Usage

```text
Use teaching-deck-review to review this deck:
[path to PPTX or PDF]

Audience: [...]
Prior knowledge: [...]
Duration: [...]
Runtime/tool/version: [...]
Learning outcomes: [...]

Run review-first. Do not edit the source deck.
Score the baseline, cite slide/page evidence, preserve useful examples,
classify P0/P1/P2 findings, and propose the smallest fixes.
```

After approving findings:

```text
Apply only the approved findings.
Do not overwrite the source deck. Create a copy and rescore it with the same rubric.
Report regressions and all remaining unverified claims.
```

## What it checks

- Learning outcomes and learner context
- Storyline, hierarchy, and Pyramid-style headlines
- AI-slop patterns without sterilizing classroom voice
- Concept density and the rule of no more than three new concepts without practice
- Activity contracts: learner action, output, success check, debrief, time, fallback
- Technical claims that require runtime or documentation verification
- Visual/readability and rehearsal gates

## Readiness rule

The recommended gate is at least 80/100, no criterion below 60%, no unresolved P0, verified technical claims, rendered visual review, learner output for practical outcomes, and a timed rehearsal.

Missing evidence is reported as `unverified`; it is never silently converted into a passing score.

## Scope

This repository contains the reusable skill and references only. It does not include private decks, student data, screenshots, or The1ight internal vault files.
