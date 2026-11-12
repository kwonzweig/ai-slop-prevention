# Data models and code

In code, the hard-coded snapshot multiplies parts: one concept gets a second schema, type, name, or endpoint, and the copies drift apart. The literature calls the data form **schema proliferation** (InfoQ, 2026) and **near-identical object types** (Palantir Ontology guidelines); the fix in both is one canonical representation per concept, with one distinguishing property for the variants.

## One concept, one owner

| Habit | Do instead |
| --- | --- |
| A new type or table per variant (`CharacterRequest`, `SoundRequest`) | One record with a discriminator field (`tab`, `kind`). Single Table Inheritance (Fowler); one Canonical Data Model for every consumer (Hohpe and Woolf). |
| Variants that differ in shape, not only in value (minutes have attendees, call logs have a customer) | Still one record: the discriminator plus one nullable detail block per kind (a JSON column or an optional sub-object keyed by `kind`). Separate detail tables only when someone needs to query inside the block. |
| A second word for a thing that has one (request and ticket, snapshot and screenshot) | A glossary with one term per concept; the others listed under "avoid". |
| A per-variant route (`/sound/requests`) | One route with the discriminator as a filter. |
| A result, event, or history table before anyone asked | Status and owner fields on the record. A log the owner asked for is not speculative; build it, as one table for every kind. |
| Speculative flexibility: options, plugins, abstractions for a single use | The minimum that solves the task (the `karpathy-guidelines` skill: no abstractions for single-use code, no configurability that was not requested). |
| Comments that narrate the code or the session | Comments that say why, where the code cannot. |

## The legacy default

The second habit is the choice of stack. Asked what to build on, generated work proposes the option that appears most often in its training data (Express for a server, Bootstrap for styling) and calls it the simple choice. The tell is the reason given: "the project is small", "a single user", "agents know it best", "what the CTO asked for". None of these describes the option.

The same habit frames the decision inside a layer the training data has the most examples of: which HTTP framework, Express, Fastify or Hono, when the installs sit on Supabase, Convex and Prisma and the frontend's server functions make a separate API server unnecessary. The tell is the sentence that sets the platforms aside as "a different layer" or "a later decision".

Do instead: check first whether demand has moved to a component that removes the layer, and decide there. Then rank the candidates by the selection standard that the `find-tools` skill (kwonzweig/there-is-a-tool-for-that) owns, and name its numbers for the pick and for the default it displaces. Project size is never the reason for an older one.

First caught: a shared web app template, 2026-11-09. Express (about 3K skill installs) and a 1,965-star personal skill repo were chosen over options with 131K to 478K installs, with "the project is small" as the reason.

## When the brief asks for the habit

A brief that says "model each one properly with its own table and endpoints" is asking for the outcome, not the table count. Deliver the one-record design and state in one line what the per-variant version would cost (repeated handlers, a fourth endpoint for the mixed list, three audit shapes). If the owner then repeats the request, build it their way; the decision is theirs once they have seen both. Never follow the habit silently, and never refuse silently.

Values the brief leaves open (enum members, which id a field holds) are stated as assumptions in the reply, not asked as questions, when the owner is in a hurry.

## The rule of three, applied before it is too late

Before adding a type, table, interface, document, or term, answer in one line: can the existing one express this with a new value or a nullable field? If yes, do that. If two definitions share most of their fields, merge them and keep the difference as a field. Keeping them apart is a decision the owner records, not a default.

## Check before the change is shown

1. Every concept in the change has exactly one record, type, and name.
2. Every variant is a value, not a type.
3. Nothing was added for a case nobody raised.
4. A reader of the diff can name what each new line is for.
5. Every stack or library choice shows the numbers `find-tools` ranks by, for the pick and for the default it displaced.
6. No choice was made inside a layer that skill demand has left.
