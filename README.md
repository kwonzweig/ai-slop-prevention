# AI Slop Prevention

`ai-slop-prevention` is an agent skill that names the habits generated work falls into and has the agent catch them before a person sees the result: a card that chains several fields on one line, an id shown as a label, a sentence in the interface that explains the interface, a template with no list of its fields, a second schema for a concept that already has one.

It covers three media, and each reference ends with a check to run before the work is shown:

- [references/ui.md](references/ui.md): screens, cards, forms and prototypes
- [references/prose.md](references/prose.md): documents, messages, templates and report formats, next to [humanizer](https://github.com/blader/humanizer)
- [references/code.md](references/code.md): data models, schemas and stack choices

## Install

With the [skills CLI](https://github.com/vercel-labs/skills):

```bash
npx skills add kwonzweig/ai-slop-prevention
```

## License

MIT
