---
name: after-ai-text
description: Rewrites AI-assisted drafts into cleaner human text by removing neural clichés, fake-depth phrasing, and structural AI patterns. Use when the user wants to humanize writing, strip LLM-style phrasing, audit text for neural smell, or rewrite copy closer to a real voice.
---

# After AI Text

Turn AI-assisted drafts into text that reads like a real person wrote it.

## Use this skill when

- The user says a text sounds neural, robotic, templated, dry, fake-human, or too polished.
- The task is to humanize, de-AI, rewrite, or audit a draft.
- The user wants stronger voice, rhythm, specificity, or a more debatable point of view.
- The user provides writing samples and wants a closer style match.

## Modes

1. **Audit** — inspect the draft and report AI signals, clichés, structural patterns, and weak human signals.
2. **Rewrite** — rewrite the draft into a more natural human voice.
3. **Style-match** — rewrite using provided author samples.
4. **Prompt-mode** — produce a reusable prompt for another model/session.

If the request is ambiguous, default to **rewrite**.

## Default delivery

- For most real tasks, return the **clean rewritten text first**.
- Add notes only when they help the user decide what to do next.
- Use a fuller audit structure only when the user explicitly asks for an audit, diagnosis, or explanation.
- Do not force a rigid report shape onto chat-like tasks, captions, short posts, or line edits.

## Core workflow

Copy this checklist for multi-step tasks:

```markdown
Rewrite Progress:
- [ ] Step 1: Identify mode and constraints
- [ ] Step 2: Diagnose AI signals
- [ ] Step 3: Remove AI patterns
- [ ] Step 4: Restore human signals
- [ ] Step 5: Audit the result
- [ ] Step 6: Fix only failed points
```

### Step 1: Identify mode and constraints

Determine:
- target format: post, article, email, landing page, script, comment
- target length: short, medium, or long
- content category using [references/format-and-category-matrix.md](references/format-and-category-matrix.md)
- whether style samples exist
- whether personal details/facts are available
- whether the user wants only audit, only rewrite, or both

Fast routing:
- short fragment, CTA, caption, subject line, one paragraph -> fix quickly, no heavy audit dump
- medium draft -> audit mentally, rewrite, then run a light second pass
- long article, expert post, or high-stakes copy -> use the full audit loop and scoring

### Step 2: Diagnose AI signals

Check the draft against:
- [references/ai-signals-checklist.md](references/ai-signals-checklist.md)
- [references/banned-phrases-ru.md](references/banned-phrases-ru.md)
- [references/banned-phrases-en.md](references/banned-phrases-en.md)
- [references/structural-patterns.md](references/structural-patterns.md)
- [references/slop-frequency-rules.md](references/slop-frequency-rules.md)
- [references/pattern-severity.md](references/pattern-severity.md)
- [references/neural-turns-and-fake-depth.md](references/neural-turns-and-fake-depth.md)
- [references/cringe-rhetoric-patterns.md](references/cringe-rhetoric-patterns.md)
- [references/examples-good-vs-bad.md](references/examples-good-vs-bad.md)
- [references/misha-anti-patterns.md](references/misha-anti-patterns.md) when writing for Misha or calibrating toward his taste

Look for:
- cliché phrases
- formal filler openers
- flat sentence rhythm
- generic abstractions without specifics
- fake neutrality or modal hedging
- LinkedIn-style rhetorical tricks
- visual rhetoric overuse: repeated colons, em dashes, faux-dramatic paragraphing
- repeated model habits: the same structure used as the hidden template of the text
- fake-depth turns and symmetrical contrast frames
- lack of opinion, tension, or personal layer

After detecting issues, classify severity before rewriting:
- high severity: restructure first
- medium severity: rewrite the affected parts
- low severity: fix only if it improves flow

When multiple issues stack in the same paragraph, assume the wording is not the real problem. The hidden skeleton is.

### Step 3: Remove AI patterns

Delete or rewrite:
- filler phrases that announce a point instead of making it
- repeated high-level abstractions
- structural AI patterns
- repeated model habits that create the text skeleton
- fake emphasis adjectives
- empty transitions
- formal introduction/conclusion blocks unless the genre truly needs them

Do not stop at synonym replacement. If a sentence is empty, rebuild it.

When high-severity issues remain, fix structure before wording. Do not polish an empty frame.

Prefer deletion over decorative replacement. If a sentence only performs importance, transition, or pseudo-insight, cut it unless the genre truly needs that move.

### Step 4: Restore human signals

Use [references/human-writing-rules.md](references/human-writing-rules.md).

Prioritize:
- varied sentence length
- concrete facts, numbers, details, examples
- a point of view that someone could disagree with
- natural spoken syntax when appropriate
- personal experience or uncertainty only when grounded in real information
- author habits from [references/style-sampling.md](references/style-sampling.md) when samples exist

Do not invent personal experience, case studies, or facts. If the rewrite needs specifics that are missing, either:
- leave the text more neutral, or
- ask for the missing detail if it materially affects quality

Do not add random slang, deliberate typos, fake roughness, or synthetic “human texture”. Human writing is not noise. It is pressure, selectivity, and specificity.

When writing for Misha, prefer a calmer, less performative line even if it sounds slightly less literary. Avoid sentences that sound neatly packaged or proudly aphoristic.

### Step 5: Audit the result

Validate against [references/workflow-and-audit.md](references/workflow-and-audit.md).

Minimum pass criteria:
- no obvious banned phrases remain
- no obvious structural AI patterns remain
- repeated model habits are gone or clearly intentional
- rhythm is not monotone
- the text contains specifics where genre allows them
- the text has a discernible viewpoint when the task calls for it
- no fake modal hedging remains unless uncertainty is real

Use scoring from [references/workflow-and-audit.md](references/workflow-and-audit.md) for medium and long rewrites, audits, articles, expert posts, or explicit quality control requests. Skip scoring for quick line edits.

Run this short self-check before delivery:
- Which 1-3 lines still sound prebuilt?
- Where is the text still too smooth?
- Did I replace empty phrasing with actual content, or only with better-sounding emptiness?

If you can point to a suspicious line, fix it before sending.

### Step 6: Fix only failed points

Do a targeted second pass. Do not rewrite the whole draft again unless the first pass failed broadly.

## Output patterns

### Audit output

Use [assets/audit-output-template.md](assets/audit-output-template.md).

### Rewrite output

Use [assets/rewrite-output-template.md](assets/rewrite-output-template.md).

Default rewrite behavior:
- short tasks -> return only the rewritten text unless commentary is useful
- medium tasks -> rewritten text first, then 2-4 short notes if needed
- long or sensitive tasks -> rewritten text plus concise explanation of the main fixes

### Prompt-mode output

Use [assets/natural-text-system-prompt.md](assets/natural-text-system-prompt.md).

## Hard rules

- Do not optimize for “bypassing AI detectors”. Optimize for better writing.
- Do not fake human texture with random slang or filler.
- Do not over-clean to the point of sounding sterile.
- Do not preserve AI structure just because the wording changed.
- Do not claim a style match without actual samples.
- Do not invent personal facts to make the text feel human.
- Do not turn every rewrite into a lecture about AI writing.
- Do not keep template headings like `What changed` or `Notes` when the user only needs the finished text.
- Do not flatten all sharpness out of the text; remove falseness, not personality.

## When samples are provided

Read [references/style-sampling.md](references/style-sampling.md) and extract:
- sentence rhythm
- favorite transitions and openings
- level of sharpness vs softness
- amount of colloquial language
- recurring rhetorical habits

Match the voice, not just the vocabulary.
