---
name: teaching-deck-review
description: Review and improve teaching decks with evidence.
version: 0.1.0
author: Quang Nguyen, Hermes Agent
license: MIT
platforms: [linux, macos, windows]
metadata:
  hermes:
    tags: [teaching, slides, review, pedagogy, ai-slop]
    related_skills: [powerpoint, humanizer, pdf, ocr-and-documents]
---

# Teaching Deck Review

Use this skill to review a near-finished teaching deck before publication, or to design a new lesson when the learning outcome is not yet clear. The default mode is review-first: inspect the real artifact, score it with evidence, preserve what works, propose the smallest useful changes, and rescore the actual output. Do not silently rewrite a deck or invent technical claims.

## When to Use

- Review an existing PPTX or PDF teaching deck.
- Detect AI slop in slide copy, headlines, structure, density, or activities.
- Apply Pyramid-style headlines without making every slide a slogan.
- Check the rule that no more than three new concepts pass without related practice.
- Compare a revised deck with a user-provided benchmark.
- Run a before/after scorecard before sharing a deck.

Do not use this skill to approve technical claims without runtime or documentation evidence, or to replace a teacher's decision about scope, audience, or voice.

## Prerequisites

Collect the deck path, audience, prior knowledge, duration, learning outcomes, runtime/tool version, and brand/template constraints. Load `powerpoint` for PPTX inspection; load `pdf` or `ocr-and-documents` for PDF benchmarks; load `humanizer` only for the copy pass. If a required fact is unavailable, mark it unverified.

## Procedure

### 1. Choose the route

- **Review-first:** a deck already exists or is nearly complete.
- **Design-first:** outcomes, audience, or lesson scope are still unresolved.

Use review-first unless changing the learning outcome or scope is necessary. Completion criterion: the chosen route and its reason appear in the report.

### 2. Inspect the real artifact

Read all available slide text, tables, notes, images, slide visibility, and timing metadata. Render or export pages when visual claims matter. Record gaps: unreadable images, missing notes, absent animation, unknown custom-show behavior, or unavailable runtime. Completion criterion: report states what was inspected and what was not.

### 3. Score before editing

Use `references/rubric.md`. Cite slide/page numbers for every non-trivial finding. Separate:

- **P0:** blocks safe or accurate teaching.
- **P1:** materially harms learning flow, clarity, or classroom execution.
- **P2:** polish after the core lesson works.

Keep a **preserve list** for strong examples, real classroom context, useful screenshots, and intentional question/reveal pairs. Do not treat duplicate-looking reveal slides as waste without checking their presentation purpose. Completion criterion: baseline score, evidence, preserve list, priorities, and unverified items are present.

### 4. Propose the smallest fix

For each accepted finding, state the smallest edit, why it helps, and how it will be verified. Do not change learning outcomes, remove real examples, or rewrite the whole deck without explicit approval. Keep technical claims separate from copy improvements. Completion criterion: every proposed change maps to an accepted finding.

### 5. Turn approved findings into a revision brief

Do not jump from a scorecard directly into rewriting. Convert only the accepted findings into a revision brief:

```text
Revision goal:
Approved findings:
Slides/sections in scope:
Preserve list:
Do not change:
Copy changes:
Structure changes:
Activity changes:
Technical claims to verify or qualify:
Timing budget:
Output path:
Verification required:
```

The brief must distinguish **must fix**, **may improve**, and **out of scope**. If a finding changes the learning outcome, audience, duration, or teaching scope, stop and request a new design decision instead of treating it as a copy edit. Completion criterion: every edit has an approved finding or is explicitly labeled necessary for consistency.

### 6. Revise a copy in passes

Write to a new output path, never over the source. Use this order:

1. **Structure pass:** fix section order, repeated slides, concept grouping, transitions, and the concept-to-practice rhythm.
2. **Learning pass:** make each demo/activity include learner action, output, success check, debrief, time, and fallback.
3. **Headline pass:** make headers state the point or learner action; check that each supporting element answers the header.
4. **Copy pass:** simplify sentences, remove AI slop, preserve necessary conditions, and keep terminology consistent. Load `humanizer` only here.
5. **Technical pass:** verify, qualify, or remove claims that depend on runtime/provider/version. Do not make unverified behavior sound more certain.
6. **Visual pass:** apply the supplied template/brand rules only after content is stable; render when the toolchain allows it.

Keep student-facing text separate from speaker notes. Questions must not reveal their answers before the reveal step. Do not delete useful examples, classroom context, or intentional question/reveal pairs without an accepted finding. Completion criterion: output path exists, every changed slide is listed, and each approved finding maps to a change or a documented reason it was not changed.

### 7. Run revision QA before rescore

Read the revised artifact as a fresh reviewer, not from the editor's summary. Check:

- approved findings are actually resolved;
- no preserve-list item disappeared without approval;
- learning outcomes still have evidence;
- no new claim, contradiction, or timing overflow was introduced;
- question/reveal order works in slideshow mode;
- notes/student-facing content remain separated;
- source file is unchanged.

Completion criterion: a revision QA list marks each approved finding resolved, partial, or not resolved, plus regressions and unverified checks.

### 8. Rescore the output

Run the same rubric on the actual revised artifact, not only on the editor's summary. Compare baseline/current scores, resolved findings, remaining findings, and regressions. Completion criterion: before/after table and remaining P0/P1/P2 list are present.

### 7. Gate readiness

Do not call a deck ready-to-teach until all are true:

- score is at least 80/100 and no criterion is below 60%;
- no P0 remains;
- runtime claims are verified or explicitly removed/qualified;
- visual readability is checked on rendered output;
- each practical outcome has learner output and a success check;
- timing includes instructions, doing, debrief, transitions, and buffer;
- a rehearsal or timed run-through has been recorded.

If a gate is unavailable, report `unverified`; never convert missing evidence into a pass.

## Reference Files

- `references/rubric.md` — scorecard, thresholds, and evidence rules.
- `references/teaching-style.md` — benchmark style distilled from the user's approved deck.
- `references/activity-design.md` — demo/activity rhythm and activity contract.
- `references/review-report-template.md` — required report shape.

## Pitfalls

- Counting slides instead of concepts.
- Calling a screenshot an activity when the learner has no task or output.
- Using `humanizer` to remove useful classroom questions, humor, or reveal structure.
- Treating a benchmark deck as proof that every technical claim is correct.
- Giving points for unverified runtime or visual criteria.
- Letting a rewrite erase useful context or examples.
- Editing the original deck before baseline review and approval.

## Verification

Verify the source and output paths, slide/page counts, changed-slide list, before/after scorecard, remaining unverified claims, and gate status. State exactly which checks were not possible.
