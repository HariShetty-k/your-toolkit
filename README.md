# your-toolkit

A collection of skills and reference docs for AI agents, packaged as a Claude Code plugin.

## Install as a Claude Code plugin

In Claude Code, run:

```
/plugin marketplace add HariShetty-k/your-toolkit
/plugin install your-toolkit@your-toolkit
/plugin install 21st@your-toolkit
```

The `21st` plugin is the official [21st.dev](https://21st.dev) plugin, listed here so you can install everything from one place. It needs a free API key from [21st.dev/mcp](https://21st.dev/mcp), saved in the `API_KEY_21ST` environment variable.

Then, in any project, ask things like "set up the product doc", "make it look like Linear", or "map the user journey", or call a skill directly:

| Skill | What it does |
|-------|--------------|
| `/your-toolkit:product` | Writes `PRODUCT.md`: what you're building, for whom, and why |
| `/your-toolkit:design` | Adds a `DESIGN.md` from the [awesome-design-md](https://github.com/voltagent/awesome-design-md) collection, or writes a custom one. When building UI, it uses 21st.dev components and the `motion` skill, restyled to match `DESIGN.md` |
| `/your-toolkit:architecture` | Writes `ARCHITECTURE.md`: stack, codemap, data model, key flows, decisions, and rules |
| `/your-toolkit:motion` | Adds animation with Motion (formerly Framer Motion), matched to `DESIGN.md` |
| `/your-toolkit:user-journey` | Writes `USER-JOURNEY.md`: personas, journey stages, and key flows |
| `/21st:21st-ui` | From the `21st` plugin: finds and installs 21st.dev components, and generates UI |

## Templates

| File | Purpose |
|------|---------|
| [`product.md`](product.md) | Product context: what we're building, for whom, and why |
| [`design.md`](design.md) | Design references, based on [awesome-design-md](https://github.com/voltagent/awesome-design-md) |
| [`user-journey.md`](user-journey.md) | User journey: personas, journey stages, and key flows |
| [`architecture.md`](architecture.md) | Architecture: stack, codemap, data model, decisions, and rules |
