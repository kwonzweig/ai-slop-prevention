---
name: ai-slop-prevention
license: MIT
description: 'Use when building, modifying, or reviewing UI, including work based on supplied examples; when reviewing other deliverables; and before showing or handing off a document, message, prompt, spec, game content, data model, or code. Triggers include unlabeled fields, off-target content, redundant explanations, or stack choices based on familiarity.'
---

# AI slop prevention

Read the reference for the medium you are producing. Each one ends with a check to run before the work is shown.
When building, modifying, or reviewing UI, read and apply [references/ui.md](references/ui.md) before making design or implementation decisions.

| Deliverable | Read |
| --- | --- |
| A screen, card, list, form, caption, button, empty state, or prototype | [references/ui.md](references/ui.md) |
| Prose a person reads: document, message, spec, template or report format, commit, release note, in-game text | [references/prose.md](references/prose.md) |
| A data model, schema, API, or code structure | [references/code.md](references/code.md) |

## Prose, code, and shared habits

| Habit | What a person sees | Do instead |
| --- | --- | --- |
| Field mash | Fields of different kinds chained with dots, pipes, or spaces; a template or report format with no list of its fields | One field per labeled line or cell. A template or report format opens with its fields and their types. See [prose.md](references/prose.md). |
| Off-target entries | A result that answers a question carries things that do not meet it, often with a note that says so: a catalog snapshot listed as "no source list here" in a reply about where the sources are | The result holds every entry that meets the question, and only those. The rest of the investigation stays in the notes. See prose.md. |
| Staged prose | not X but Y, one-line closers, forced triads, dashes everywhere, bold labels, "I hope this helps" | Say the thing once, plainly. See prose.md. |
| Legacy default | The option most common in training data (Express, Bootstrap) proposed as the simple choice, with "the project is small" or "agents know it best" as the reason; or the decision framed inside a layer that demand has left | Check first whether demand has moved to a component that removes the layer, and decide there. Then rank the candidates by the standard in `find-tools`. Project size is never the reason for an older one. See code.md. |

## What this skill owns, and what it points to

The medium references own this skill's rules. For related work, use these skills when installed:

| Slice | Skill |
| --- | --- |
| Prose tells | `humanizer` (blader/humanizer) |
| Visual tells of generated pages: gradients, kicker labels, fake stats, card nesting | `antislop-ui` (miqdadbadjuber/anti-slop) or `hallmark` (Nutlope/hallmark, whose floor rule 10 bans middle-dot meta strings) |
| UX copy that restates the control or exposes internal codes | `impeccable` clarify reference (pbakaus/impeccable) |
| Comment hygiene and over-engineering in code | `antislop-code` (miqdadbadjuber/anti-slop), `unslop-ai-code` (JCarterJohnson/vibecoded-design-tells) |
| Stack and tool choice | `find-tools` (kwonzweig/there-is-a-tool-for-that) |
| Copying what an owner holds instead of pointing to it: a README listing a catalog's sources, a description or count typed into a repo | `reality-sense` (kwonzweig/reality-sense), Single source of truth |

## Adding a habit

A habit enters this skill when the owner of a deliverable names it, or when a with-skill test shows agents producing it. The entry records what a person sees, what to do instead, and the first place it was caught in the medium's reference file. The table above covers prose, code, and shared habits only. The engine or product skill that was being built does not get the rule; it points here. Push, then refresh wherever the skill is installed (company skill sources, local skill folders).
