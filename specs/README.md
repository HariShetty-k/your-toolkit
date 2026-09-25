# Specs

One folder per feature, numbered in order:

```
specs/
├── 001-user-signup/
│   ├── spec.md    # what and why: user stories and acceptance criteria
│   ├── plan.md    # how: technical approach, files to change
│   └── tasks.md   # the checklist, ticked off as work is done
└── _template/     # copy this to start a new spec
```

Flow: **spec → plan → tasks → code**. Get the spec agreed before writing the plan, and the plan agreed before writing code.

With Claude Code, use the `spec` skill ("write a spec for signup") to create a new folder from `_template/`.
