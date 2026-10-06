<div align="center">

# your-toolkit

<h3>Start every repo with the docs AI agents need — and the skills to write them.</h3>

<a href="#-quick-start">Quick start</a> |
<a href="#-agent-skills">Agent skills</a> |
<a href="#-design-skills">Design skills</a> |
<a href="CHANGELOG.md">Changelog</a>

<br/><br/>

[![Claude Code plugin](https://img.shields.io/badge/Claude%20Code-plugin-D97757)](https://code.claude.com/docs/en/plugins)

</div>

your-toolkit is a Claude Code plugin that consists of two main parts:

- **[Agent skills](#-agent-skills)**: set up a repo and write the docs every AI
  coding session reads first: product, user journey, architecture, and feature specs.
- **[Design skills](#-design-skills)**: pick or write a design system, add
  animation, and pull in ready-made UI components, all matched to one `DESIGN.md`.

Every new repo starts the same way, so agents always know what you're building,
for whom, how it's built, and how it should look.

## ⚡ Quick start

Install the plugin once in Claude Code:

```
/plugin marketplace add HariShetty-k/your-toolkit
/plugin install your-toolkit@your-toolkit
```

Then, in any new or existing repo:

```
/your-toolkit:setup
```

or just ask *"set this repo up with my toolkit"*. It adds the starter files below
without overwriting anything you already have:

```
your-project/
├── CLAUDE.md          # Claude Code entry point: imports AGENTS.md, PRODUCT.md, ARCHITECTURE.md
├── AGENTS.md          # Instructions for any AI coding tool: docs map, commands, workflow
├── PRODUCT.md         # What we're building, for whom, and why
├── ARCHITECTURE.md    # Stack, codemap, data model, decisions, and rules
├── USER-JOURNEY.md    # Personas, journey stages, and key flows
├── specs/             # One folder per feature: spec.md → plan.md → tasks.md
└── .claude/
    └── settings.json  # Plugins this project uses
```

Then fill them in, in this order:

1. `product` → `PRODUCT.md`
2. `user-journey` → `USER-JOURNEY.md`
3. `architecture` → `ARCHITECTURE.md`, then the commands in `AGENTS.md`
4. `design` → `DESIGN.md`
5. `spec` for each feature, then build

You don't have to type the commands. Each skill also runs when you ask for what
it does, for example *"write a spec for signup"* or *"make it look like Linear"*.

## 🧭 Agent skills

| Skill | What it does |
|-------|--------------|
| `/your-toolkit:setup` | Adds the starter files to a new or existing repo, merging `.claude/settings.json` and skipping docs that already exist |
| `/your-toolkit:product` | Fills in `PRODUCT.md`: what it is, who it's for, goals, features, success metrics |
| `/your-toolkit:user-journey` | Fills in `USER-JOURNEY.md`: personas, journey stages, key flows |
| `/your-toolkit:architecture` | Fills in `ARCHITECTURE.md` from the code, or proposes a stack for a new project |
| `/your-toolkit:spec` | Creates `specs/NNN-feature/` with a spec, plan, and task list before coding |

## 🎨 Design skills

| Skill | What it does |
|-------|--------------|
| `/your-toolkit:design` | Adds a `DESIGN.md` from the [design catalog](templates/design-catalog.md) (brand styles from [awesome-design-md](https://github.com/voltagent/awesome-design-md)), or writes a custom one. When building UI, it uses 21st.dev components and the `motion` skill, restyled to match `DESIGN.md` |
| `/your-toolkit:motion` | Adds animation with Motion (formerly Framer Motion), matched to `DESIGN.md` |
| `/21st:21st-ui` | From the official [21st.dev](https://21st.dev) plugin: finds and installs UI components, and generates UI |

The 21st.dev plugin is listed in this marketplace so it installs from the same
place: `/plugin install 21st@your-toolkit`. It needs a free API key from
[21st.dev/mcp](https://21st.dev/mcp), saved in the `API_KEY_21ST` environment variable.

## 🧩 Recommended plugins

The starter `.claude/settings.json` enables this toolkit, the 21st.dev plugin,
and these from Anthropic's official marketplace. Remove any you don't want.

| Plugin | What it gives you |
|--------|-------------------|
| `superpowers` | Brainstorming, planning, test-driven development, systematic debugging, and checking work before calling it done |
| `code-review` | Multi-agent pull request review |
| `commit-commands` | Commit, push, and open a pull request |
| `security-guidance` | Warns about risky code as it's written |
| `claude-md-management` | Keeps `CLAUDE.md` accurate as the project changes |

## 📁 Repository layout

```
your-toolkit/
├── .claude-plugin/
│   ├── plugin.json          # Plugin name and version
│   └── marketplace.json     # Lists your-toolkit and the 21st.dev plugin
├── skills/
│   ├── setup/               # agent  → copies templates/project/ into a repo
│   ├── product/             # agent  → PRODUCT.md
│   ├── user-journey/        # agent  → USER-JOURNEY.md
│   ├── architecture/        # agent  → ARCHITECTURE.md
│   ├── spec/                # agent  → specs/NNN-feature/
│   ├── design/              # design → DESIGN.md
│   └── motion/              # design → Motion animation patterns
├── templates/
│   ├── project/             # The starter files setup copies
│   └── design-catalog.md    # Brand design systems the design skill chooses from
├── AGENTS.md                # How to maintain this toolkit
└── CHANGELOG.md
```

To add or change a skill, see [AGENTS.md](AGENTS.md).

## Credits

The [design catalog](templates/design-catalog.md) is adapted from
[VoltAgent/awesome-design-md](https://github.com/voltagent/awesome-design-md)
(MIT License, © 2026 VoltAgent); its license notice is kept in that file.
