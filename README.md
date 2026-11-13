# AI Slop Prevention

`ai-slop-prevention` reviews the quality of deliverables people read or use: interfaces, prose, and the code and data models behind a product. It catches habits such as unlabeled fields, internal ids shown as names, and redundant explanations before delivery. Its scope is the delivered artifact; agent working methods and instruction maintenance belong to the skills that own those workflows.

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
