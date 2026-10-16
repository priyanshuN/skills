# Changelog

## 0.2.0 — 2026-10-16

- `ambition`: new skill. Makes a request more ambitious along altitude (ask for the outcome),
  depth (expert instruments, raw material, an outside judge) and range (methods from other
  fields), and drops a lens with one line when it does not fit.
- `range-scout`: first agent (`kit:range-scout`). Restates a task as verbs and returns 2–4
  outside fields with a concrete method, raw material and likely finding each.
- `evals/`: first eval suite, five cases covering the three lenses, restraint on a trivial
  task, and the agent.

## Catalog — 2026-10-11

- The `skills` marketplace also lists `diagrams` (from its own repo) and `triago` (from npm).

## 0.1.0 — 2026-10-11

- `handoff`: first skill (moved from a private repo). Reads the inbox URL and device from
  `~/.config/handoff/config.json`; `setup` can publish a new inbox from `assets/inbox.html`.
