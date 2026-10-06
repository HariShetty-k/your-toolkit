# your-toolkit

A starter kit for AI-assisted projects in two parts:

1. **A project template.** The docs every project needs (product, architecture,
   user journey, specs) wired up so Claude Code and other AI coding tools read
   them automatically.
2. **A Claude Code plugin.** Six skills that fill those docs in, plus a design
   catalog and animation guidance for building the UI.

## Contents

- [Quick start](#quick-start)
- [What's in the repo](#whats-in-the-repo)
- [Skills](#skills)
- [Recommended plugins](#recommended-plugins)
- [Suggested order for a new project](#suggested-order-for-a-new-project)
- [Updating the toolkit](#updating-the-toolkit)

## Quick start

**Start a new project from the template.** On GitHub, click **Use this template →
Create a new repository**, then open the new repo in Claude Code and trust the
folder. Claude Code registers this marketplace and offers to install the plugins
listed in `.claude/settings.json`.

**Add the skills to an existing project.** In Claude Code, run:

```
/plugin marketplace add HariShetty-k/your-toolkit
/plugin install your-toolkit@your-toolkit
/plugin install 21st@your-toolkit
```

The `21st` plugin is the official [21st.dev](https://21st.dev) plugin, listed here
so everything installs from one place. It needs a free API key from
[21st.dev/mcp](https://21st.dev/mcp), saved in the `API_KEY_21ST` environment variable.

## What's in the repo

### Project template: copied into every new project

```
├── CLAUDE.md          # Claude Code entry point: imports AGENTS.md, PRODUCT.md, ARCHITECTURE.md
├── AGENTS.md          # Instructions for any AI coding tool: docs map, commands, workflow
├── PRODUCT.md         # What we're building, for whom, and why
├── ARCHITECTURE.md    # Stack, codemap, data model, decisions, and rules
├── USER-JOURNEY.md    # Personas, journey stages, and key flows
├── specs/
│   ├── README.md      # How specs work: spec → plan → tasks → code
│   └── _template/     # spec.md, plan.md, tasks.md to copy per feature
└── .claude/
    └── settings.json  # Marketplaces and plugins this project uses
```

`DESIGN.md` isn't in the template. The `design` skill adds it once you pick a look.

### Claude Code plugin: the skills

```
├── .claude-plugin/
│   ├── plugin.json        # Plugin name, version, author
│   └── marketplace.json   # Lists your-toolkit and the 21st.dev plugin
├── skills/
│   ├── product/           # → PRODUCT.md
│   ├── user-journey/      # → USER-JOURNEY.md
│   ├── architecture/      # → ARCHITECTURE.md
│   ├── design/            # → DESIGN.md
│   ├── spec/              # → specs/NNN-feature/
│   └── motion/            # Motion animation patterns
└── templates/
    └── design-catalog.md  # Brand design systems the design skill chooses from
```

The skills use the root template files (`PRODUCT.md`, `ARCHITECTURE.md`,
`USER-JOURNEY.md`, `specs/_template/`) as their blank forms, so the two parts
stay in one repo. In a project created from the template, the plugin files are
harmless; delete `.claude-plugin/`, `skills/` and `templates/` if you like.

## Skills

| Skill | What it does |
|-------|--------------|
| `/your-toolkit:product` | Fills in `PRODUCT.md` |
| `/your-toolkit:user-journey` | Fills in `USER-JOURNEY.md` |
| `/your-toolkit:architecture` | Fills in `ARCHITECTURE.md` from the code, or proposes a stack for a new project |
| `/your-toolkit:design` | Adds a `DESIGN.md` from the [awesome-design-md](https://github.com/voltagent/awesome-design-md) collection, or writes a custom one. When building UI, it uses 21st.dev components and the `motion` skill, restyled to match `DESIGN.md` |
| `/your-toolkit:spec` | Creates `specs/NNN-feature/` with a spec, plan, and task list |
| `/your-toolkit:motion` | Adds animation with Motion (formerly Framer Motion), matched to `DESIGN.md` |
| `/21st:21st-ui` | From the `21st` plugin: finds and installs 21st.dev components, and generates UI |

You don't have to type the commands. Each skill also runs when you ask for what
it does, for example "write a spec for signup" or "make it look like Linear".

## Recommended plugins

`.claude/settings.json` also enables these from Anthropic's official marketplace
(`claude-plugins-official`):

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

## Updating the toolkit

- Skills live in `skills/<name>/SKILL.md`. To add one, create a new folder with a
  `SKILL.md` that has `name` and `description` front matter, and add it to the
  table above.
- After changing a skill, bump `version` in `.claude-plugin/plugin.json` so
  installed copies pick up the update (`/plugin marketplace update your-toolkit`).
- Keep `main` as the only long-lived branch; the marketplace installs from it.

## License

[MIT](LICENSE). The design catalog is adapted from
[VoltAgent/awesome-design-md](https://github.com/voltagent/awesome-design-md), also MIT.
