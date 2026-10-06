# AGENTS.md

Instructions for AI coding agents working on **your-toolkit itself**. The files in
`templates/project/` are blank starter docs for *other* repos: don't fill them in
here, and don't treat them as describing this repo.

## Layout

| Path | What it is |
|------|------------|
| `.claude-plugin/plugin.json` | Plugin name, version, description |
| `.claude-plugin/marketplace.json` | Marketplace listing: this plugin and the 21st.dev plugin |
| `skills/<name>/SKILL.md` | One skill per folder, flat (no nesting), with `name` and `description` front matter |
| `templates/project/` | Starter files the `setup` skill copies into a project |
| `templates/design-catalog.md` | Brand design systems the `design` skill chooses from |

Skills reach templates with paths relative to their own folder, e.g.
`../../templates/project/PRODUCT.md`. If you move a template, update every skill
that points to it (`grep -rn '\.\./\.\./' skills/`).

## Making a change

1. Edit the skill or template.
2. Bump `version` in `.claude-plugin/plugin.json`: minor for a new skill or
   template, patch for a fix or wording change.
3. Add an entry at the top of `CHANGELOG.md`.
4. If a skill was added, renamed or removed, update the skill tables in
   `README.md` and the skill list in `templates/project/CLAUDE.md`.
5. Commit to `main`. It's the only branch, and the marketplace installs from it.

## Writing skills

- The `description` decides when Claude uses the skill: say what it does and the
  phrases that should trigger it.
- Steps are numbered and concrete. Never overwrite a user's existing file without asking.
- Write "TBD" for unknowns in templates rather than inventing content.
