# Prose

Prose a person reads: a document, a message, a spec, a commit message, a release note, in-game text, a tooltip. The full catalogue of tells and the rewrite method live in the `humanizer` skill (Wikipedia's "Signs of AI writing", maintained by WikiProject AI Cleanup). When humanizer is installed, use it; this page is the short form for when it is not, and for what humanizer does not cover.

## The tells that justify a rewrite on one sighting

- Not X but Y, including the split form ("This does not mean X. It means Y.") and the clipped tail ("…, no guessing").
- A one-line closer that restates the paragraph ("That is the real win.").
- Staged run-ups ("Let's dive in", "Here's the thing").
- Arguing with nobody ("To be clear", "I'm not saying").
- Forced triads, dashes as the universal connector, bold labels on every bullet, title-case headings, emoji markers.
- Chatbot residue ("I hope this helps", "Would you like…").
- Writing about the document instead of its subject ("this section is organized by…").

## A result holds what was asked for

A list, table or summary that answers a question holds every entry that meets the question, and only those, however few or many that makes it. Before the reply is shown, go through the notes: each finding that meets the question goes in, and each that does not stays in the notes. An entry whose own text says it does not meet the question ("no source list here", "doesn't sell pasta") is this habit: the writer saw the mismatch and kept the entry. When nothing meets the question, say that in one sentence.

Research names it: DeepSearchQA (Google DeepMind, 2026) counts "extraneous answers", agents drifting into adjacent topics after they have the answer, and Padding to k (2026) shows models filling a list toward a count they were shown.

First caught: 2026-11-11. Asked which sources agent stack research uses and which repo holds them, a reply listed a catalog snapshot with the note "no source list here". Five of five fresh runs on the same notes did the same.

## What humanizer does not cover and this skill does

- **Interface copy** is not prose. A label, a button, a tooltip, an empty state follow [ui.md](ui.md): one fact, no coaching, no explanation of the control.
- **Templates, report formats, and records written for machines and people at once** (a task-board comment, a log line, a commit): the template opens with its field list, one row per field giving its name and type: an enum with its allowed values, a number, a date or time, a link, or text. The form below it puts one field per labeled line or table cell, in that order, so `Owner: Level Designer` is never folded into a sentence with three other facts. Free text goes only in a field typed text. First caught: 2026-11-11, code-review comment templates written without field types in 10 of 10 runs.
- **Korean**: keep technical names in English (repo, PR, issue, skill) and do not translate them into near-synonyms; the `humanize-korean` skill holds the Korean-specific tells when installed.

## Check before the text is shown

1. Every sentence adds a fact the reader did not have.
2. No tell from the list above survives.
3. Facts that belong in fields are in fields, not in a sentence.
4. Every entry in a list, table or summary meets the question it answers, and every finding that meets it is there.
