# skills

Small Claude Code skills in one plugin called **kit**. MIT licensed; use freely. Install it once on each
computer; every skill added here then reaches all of them.

This repo is also the catalog for everything I publish for Claude Code:

| Plugin | Lives in | What it does |
|---|---|---|
| `kit` | this repo | Small skills. `/kit:handoff` passes a prompt or session context between two computers through a private claude.ai artifact. `/kit:ambition` makes a request more ambitious (altitude, depth, range); the `kit:range-scout` agent finds methods from outside fields |
| `diagrams` | [priyanshuN/diagrams](https://github.com/priyanshuN/diagrams) | Flow and sequence diagrams as chat text, pictures and narrated walkthroughs |
| `triago` | [priyanshuN/triago](https://github.com/priyanshuN/triago) (npm `@triago/cli`) | Triage an agent's findings in a browser, one keystroke per item |

## Install (once per computer)

```
/plugin marketplace add priyanshuN/skills
/plugin install kit@skills
/plugin install diagrams@skills      # optional
/plugin install triago@skills        # optional
```

Install each plugin from one catalog only. Installing `diagrams` from both this catalog and
its own repo gives two copies of every skill.

## Ship a change

```
[edit skill] ─► [bump version in plugin.json + CHANGELOG] ─► [push]
            ─► [other computer: /plugin marketplace update skills]
```

Only a version bump ships. A push without one never reaches the other computer.

## Rules for every skill here

- Write it as if it could go public later: no personal paths, work names or private links
  inside `SKILL.md`. Per-computer values live in `~/.config/<skill>/config.json`.
- One folder per skill under `skills/`, with `SKILL.md` plus any `assets/` or `scripts/`.
  Subagents live in `agents/<name>.md` and are called as `kit:<name>`.
- Evals live in `evals/<case>/` (`prompt.md` + `graders/`). Run them before a version bump:
  `claude plugin eval . --trust-plugin -j 4`. The default run also scores a no-plugin
  baseline, so the report shows what each skill adds.
- When a skill grows code, tests or a public audience, move it to its own repo:
  `git subtree split --prefix=skills/<name>`, push to a new repo, add its own
  `.claude-plugin/`, then delete the folder here and bump the version.
