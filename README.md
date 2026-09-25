# your-toolkit

A collection of skills and reference docs for AI agents, packaged as a Claude Code plugin.

## Install as a Claude Code plugin

In Claude Code, run:

```
/plugin marketplace add HariShetty-k/your-toolkit
/plugin install your-toolkit@your-toolkit
```

Then, in any project, ask things like "set up the product doc", "make it look like Linear", or "map the user journey", or call a skill directly:

| Skill | What it does |
|-------|--------------|
| `/your-toolkit:product` | Writes `PRODUCT.md`: what you're building, for whom, and why |
| `/your-toolkit:design` | Adds a `DESIGN.md` from the [awesome-design-md](https://github.com/voltagent/awesome-design-md) collection, or writes a custom one |
| `/your-toolkit:user-journey` | Writes `USER-JOURNEY.md`: personas, journey stages, and key flows |

## Templates

| File | Purpose |
|------|---------|
| [`product.md`](product.md) | Product context: what we're building, for whom, and why |
| [`design.md`](design.md) | Design references, based on [awesome-design-md](https://github.com/voltagent/awesome-design-md) |
| [`user-journey.md`](user-journey.md) | User journey: personas, journey stages, and key flows |
