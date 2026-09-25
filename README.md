# your-toolkit

A starter template for AI-assisted projects, and a Claude Code plugin with the skills to fill it in.

## Use it as a template

Create a new repo from this template on GitHub. You get:

```
├── CLAUDE.md          # Claude Code instructions: imports AGENTS.md, PRODUCT.md, ARCHITECTURE.md
├── AGENTS.md          # Instructions for any AI coding tool: docs map, commands, workflow
├── PRODUCT.md         # What we're building, for whom, and why
├── ARCHITECTURE.md    # Stack, codemap, data model, decisions, and rules
├── USER-JOURNEY.md    # Personas, journey stages, and key flows
├── specs/             # One folder per feature: spec.md → plan.md → tasks.md
└── .claude/
    └── settings.json  # Plugins this project uses
```

`DESIGN.md` is added by the `design` skill once you pick a look.

The template repo also carries the plugin files (`.claude-plugin/`, `skills/`, `templates/`). They're harmless in a new project; delete them if you like.

When you open the new repo in Claude Code and trust the folder, it registers this marketplace and asks you to install the plugins listed in `.claude/settings.json`.

## Install the plugins by hand

In Claude Code, run:

```
/plugin marketplace add HariShetty-k/your-toolkit
/plugin install your-toolkit@your-toolkit
/plugin install 21st@your-toolkit
```

The `21st` plugin is the official [21st.dev](https://21st.dev) plugin, listed here so you can install everything from one place. It needs a free API key from [21st.dev/mcp](https://21st.dev/mcp), saved in the `API_KEY_21ST` environment variable.

| Skill | What it does |
|-------|--------------|
| `/your-toolkit:product` | Fills in `PRODUCT.md` |
| `/your-toolkit:architecture` | Fills in `ARCHITECTURE.md` from the code, or proposes a stack for a new project |
| `/your-toolkit:design` | Adds a `DESIGN.md` from the [awesome-design-md](https://github.com/voltagent/awesome-design-md) collection, or writes a custom one. When building UI, it uses 21st.dev components and the `motion` skill, restyled to match `DESIGN.md` |
| `/your-toolkit:user-journey` | Fills in `USER-JOURNEY.md` |
| `/your-toolkit:spec` | Creates `specs/NNN-feature/` with a spec, plan, and task list |
| `/your-toolkit:motion` | Adds animation with Motion (formerly Framer Motion), matched to `DESIGN.md` |
| `/21st:21st-ui` | From the `21st` plugin: finds and installs 21st.dev components, and generates UI |

## Recommended plugins

`.claude/settings.json` also enables these from Anthropic's official marketplace (`claude-plugins-official`):

| Plugin | What it gives you |
|--------|-------------------|
| `superpowers` | Brainstorming, planning, test-driven development, systematic debugging, and checking work before calling it done |
| `code-review` | Multi-agent pull request review |
| `commit-commands` | Commit, push, and open a pull request |
| `security-guidance` | Warns about risky code as it's written |
| `frontend-design` | Anthropic's skill for polished, distinctive UI |
| `claude-md-management` | Keeps `CLAUDE.md` accurate as the project changes |

Remove any you don't want from `.claude/settings.json`.

## Suggested order for a new project

1. `product` → `PRODUCT.md`
2. `user-journey` → `USER-JOURNEY.md`
3. `architecture` → `ARCHITECTURE.md`, then fill in the commands in `AGENTS.md`
4. `design` → `DESIGN.md`
5. `spec` for each feature, then build
