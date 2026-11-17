---
name: ai-slop-prevention
license: MIT
description: 'Use when building, modifying, or reviewing UI, including work based on supplied examples; when reviewing other deliverables; and before showing or handing off a document, message, prompt, spec, game content, data model, or code. Triggers include unlabeled fields, off-target content, redundant explanations, copied source lists, or stack choices based on familiarity.'
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
| Hard-coded snapshot | What an owner holds, copied as it stood at one moment: a README naming six of a catalog's seven sources, "buy meat" passed on as three cuts, a second schema or term for a concept that has one | A pointer to the owner, plus only what the reader cannot get by following it. See below; for schemas, code.md. |
| Legacy default | The option most common in training data (Express, Bootstrap) proposed as the simple choice, with "the project is small" or "agents know it best" as the reason; or the decision framed inside a layer that demand has left | Check first whether demand has moved to a component that removes the layer, and decide there. Then rank the candidates by the standard in `find-tools`. Project size is never the reason for an older one. See code.md. |

## Hard-coded snapshot

When the thing already has an owner the reader can reach (a file, a catalog, a table, a type, a skill, the words of whoever asked), point to it and add only what the reader cannot get by following the pointer. "Use X" stays "use X", in an instruction, README, skill, prompt, data record, or diagram alike. A copied detail is a second source: it goes stale when the owner changes, and the next reader takes it as complete. In code and data, pointing means reading the owner when the value is used, with a runtime cache at most; a script that writes the owner's values into repo files makes the same copy. A restriction an agent added, such as a test that forbids network access, does not make the owner unreachable; raise it with whoever owns the work. When the reader cannot reach the owner at the time of use, as with a printed handout or a kiosk with no internet, copy, and name the owner and the date beside the copy.

First caught: a README naming six of a catalog's seven sources, 2026-11-10.

## What this skill owns, and what it points to

The medium references own this skill's rules. For related work, use these skills when installed:

| Slice | Skill |
| --- | --- |
| Prose tells | `humanizer` (blader/humanizer) |
| Visual tells of generated pages: gradients, kicker labels, fake stats, card nesting | `antislop-ui` (miqdadbadjuber/anti-slop) or `hallmark` (Nutlope/hallmark, whose floor rule 10 bans middle-dot meta strings) |
| UX copy that restates the control or exposes internal codes | `impeccable` clarify reference (pbakaus/impeccable) |
| Comment hygiene and over-engineering in code | `antislop-code` (miqdadbadjuber/anti-slop), `unslop-ai-code` (JCarterJohnson/vibecoded-design-tells) |
| Stack and tool choice | `find-tools` (kwonzweig/there-is-a-tool-for-that) |

## Adding a habit

A habit enters this skill when the owner of a deliverable names it, or when a with-skill test shows agents producing it. The entry records what a person sees, what to do instead, and the first place it was caught in the medium's reference file. The table above covers prose, code, and shared habits only. The engine or product skill that was being built does not get the rule; it points here. Push, then refresh wherever the skill is installed (company skill sources, local skill folders).
