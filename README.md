# skills

My small Claude Code skills, in one plugin called **kit**. Install it once on each
computer; every skill added here then reaches all of them.

| Skill | What it does |
|---|---|
| `/kit:handoff` | Pass a prompt or session context between my Mac and my work laptop through a private claude.ai artifact |

## Install (once per computer)

```
/plugin marketplace add priyanshuN/skills
/plugin install kit@skills
```

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
- When a skill grows code, tests or a public audience, move it to its own repo:
  `git subtree split --prefix=skills/<name>`, push to a new repo, add its own
  `.claude-plugin/`, then delete the folder here and bump the version.
