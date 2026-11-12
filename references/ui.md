# Screens

Rules for anything a person operates or scans: a screen, a card, a caption, a list, a form, a prototype. Sources are given where a design system or usability study states the rule; the rest is the owner's standing decision for their products.

## One field, one label, one line

A record field is shown as a label followed by its value, on its own line or in its own cell. Fields of different kinds are never chained into one string with middle dots, pipes, slashes, or spaces.

```
Owner       Level Designer (7c1e0a42)
Requested   2026-10-28 14:02
Snapshot    Version 2
```

Not: `Owner · AI agent · Level Designer · 2026-10-28 14:02 · Snapshot`.

The test: cover the labels and ask whether a stranger can still tell which token is which field. If not, the line is a mash. A short run of same-kind items (three genre tags, two file names, `3 min read · 2 days ago`) may sit on one line, because the reader needs no label to tell them apart; that is the only use of the dot-joined meta line.

Why: Nielsen's heuristics 2 and 6 (words the user knows; information visible rather than recalled). The key/value form is the GOV.UK Design System "Summary list" and Shopify Polaris "Description list". Baymard's spec-sheet study found readers losing the link between a label and its value even when both were present; removing the label makes it worse. Anthropic's frontend-design skill lists "meta strings joined with middle dots" among the tells of generated chrome; Hallmark's floor rule 10 bans them outright; airtaxi/frontend-slop-guard rule 11 shows the Korean case (a list of roles such as design, development and operations joined with middle dots) and asks for layout instead of separators. No design system names this habit; the name used here, field mash, is this skill's own.

A field that holds a person or an agent shows its name: `Level Designer`, `Claude Code`. The kind of worker is not a separate token; it is already in the name. An id goes in parentheses after the name only when the owner asked to see it.

## Metadata nobody uses stays off the screen

A record id, an internal kind, a sequence number, a foreign key: the backend and the agents need them, the person never does. A Reddit reader never sees a post id. So `T-RG-003`, `R-007`, `worker-agent` do not appear on the screen, in a caption, or in a tooltip. Show the thing by its name (`Option 1: wider angle, added signpost`, `Version 2`, the request's own words). The one exception is a value the person will type or paste somewhere else, and then it gets its own labeled row with a copy icon.

## Collapsed is truncated, expanded is whole

A list of things written by a person (requests, messages, comments) shows each item's text truncated to one line when collapsed and in full when expanded. A separate title line exists only when someone wrote a title; it is never the first sentence copied out of the body, and the body is never repeated under a title that equals it.

Why: the Home Office design system allows "ID" only where users are shown to understand it; the implementation model (Cooper) leaking into the interface is the classic sign of a screen built from the table rather than from the task.

## Basic actions are icons

Edit, delete, save, cancel, add, duplicate, and close are icon buttons with the standard glyphs (pencil, trash, check, cross, plus, two overlapping squares, cross). Each carries an accessible name and a tooltip with the same word, so a screen reader and a hovering mouse both get it. Text buttons are for actions that have no standard glyph (Apply changes, Improve it) and for the primary action of a form such as sending a message. One action row is all icons or all text, never a mix; when one action in a row has no glyph, give the row text or move that action out.

A destructive icon asks once, in place, with a short question and the same check and cross icons. It never asks through a browser dialog.

What the design systems say, so the choice is made knowingly: Material 3 uses icon buttons for "common, easily understandable actions" and requires the tooltip to name the action; Atlassian requires a clear name on every icon button and keeps important actions as text; Apple's guidelines allow familiar icons and prefer text where a short label is clearer; NN/g found icon-only controls fail when the icon is not universal. Pencil, trash, and plus are universal. Check and cross for save and cancel are the owner's decision here, kept readable by the accessible name and tooltip.

## Form shows behaviour; words go behind an info icon

No sentence in the interface tells the reader how the interface works. A button's label says what it does; its result is visible when it happens. When an explanation is genuinely needed (an agent's procedure, a rule the person agreed to), it sits behind an info icon and appears on hover, on focus, and on tap, never as running text beside the control. A `title` attribute alone is not enough: touch screens have no hover, so the icon must also open the text as a small popover on tap and close it on the next tap or Escape.

Not: "Suggested prompts. Tap one to send it as a request, with what you have typed added to its fixed sentence." beside a chip. Instead: the chip, and an info icon whose tooltip holds that sentence.

A brief that places a helper sentence "under the status" is asking for the information to be available there, and an info icon in that spot answers it. A one-line meta row asked for "like most tools do" is the habit asking for itself; deliver labeled rows, say in one line why, and switch only if the owner repeats the request.

## No permission theatre

A value the person cannot change is shown as text. No lock glyph, no greyed-out control, no helper sentence or tooltip saying who may change it. A control that looks editable must be editable; plain text is what "obviously not editable" looks like.

## Status is an icon and a word

A status shows as its glyph followed by its word (`✓ Done`, `○ Open`). Define the glyph for every value once; never leave a state without one for others to invent.

## Names for things, not codes

A proposal has a one-line name written for the person who will choose among proposals. A game has its title. A tab has the label the person chose. Codes (`RG`, `PZ`) exist inside ids and never appear as headings or options.

## Dates say what they are

A timestamp carries its field name (`Requested`, `Edited`, `Captured at`). A bare date on a card is a date of nothing.

## Empty states state the fact

"No requests yet." is complete. The composer below it is the instruction. Coaching sentences ("Write your first request below", "Tap the star in Explore to add one") repeat what the screen already shows.

## Template chrome

The looks that generated pages fall into when nothing was chosen: cream background with a serif display and terracotta accent; near-black with one acid accent; a purple-to-blue gradient hero; Inter or Space Grotesk as the safe face; emoji as section markers; numbered 01/02/03 markers on content that is not a sequence; a card with border, radius, and shadow around every block; everything centered. None of these is wrong when chosen for the subject. All of them are wrong as arrivals.

## Color carries meaning, and real products set the bar

A screen where every icon, status, and button is the same muted grey reads as unfinished and hides the one thing the person must find: which control does what. Confirm is green, destructive and cancel are red, the selected or primary thing is the accent, status words sit on a tinted pill. This is the convention of the products people already use (GitHub, Linear, Notion, Slack, Reddit, Stack Overflow), so before styling a card, a thread, a confirm row, or a list, open two or three products of the same type and match their legibility: where they put color, how large their type is, how they show author and time, how they separate replies. Borrow the conventions, not the brand. A grey check next to a grey cross in a delete confirmation is the failure case.

## Text does not float

Every block of text and every group of controls sits inside a visible container: a card, a panel, a boxed caption. A reader must be able to tell where one thing ends and the next begins without reading. Captions under an image, the action row for a proposal, the metadata of a post, the reply under a request: each gets its own border or surface. Floating lines of text between unrelated elements are the generated look at its most recognizable.

## Check before the screen is shown

Read it as a stranger who knows the domain but not this app.

1. Every value has a label or an unmistakable form. A count without names ("2 files") is a value and needs no list.
2. No line holds two fields of different kinds.
3. No id, kind, or sequence number is on the screen at all.
4. Edit, delete, save, cancel, add are icons with names and tooltips.
5. No sentence explains the interface; explanations live behind an info icon.
6. Nothing looks editable that is not, and nothing says "you cannot".
7. Every status value has its glyph and word.
8. Each empty state is one factual sentence.
9. No text appears twice on one card.
10. Confirm, destructive, selected, and status each have their color, checked against a real product of the same type.
11. No text or control group floats outside a visible container.
