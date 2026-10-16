---
name: ambition
description: Make a task or prompt more ambitious along three axes — Altitude (ask for the outcome, not the task), Depth (do it the way the best expert would, judged by something outside the model) and Range (bring in methods from fields the task does not obviously need). Use when I say "make this more ambitious", "go deeper", "what would an expert do", "rewrite this prompt", or `/kit:ambition <task>`; when I ask which other fields, disciplines or outside perspectives should shape a piece of work; and when scoping or designing a non-trivial piece of work before starting it.
---

# Ambition

Based on Felix Rieseberg, *How to be more ambitious: a tutorial for humans with models*
(felixrieseberg.com, 2026-10-13). Speed — the same work, faster — is the fourth axis; it needs no
help, so it is not here.

The output is a better request, not a bigger one. Each lens below either changes the request or is
dropped with one line on why it does not fit this task.

## Altitude — ask for the outcome

- Ask what should happen after the task is done: the goal beyond the goal. "Fix this crash" becomes
  "keep this app crash-free".
- A good sign that altitude fits: the work will be discussed in a meeting, or the same kind of task
  keeps coming back.
- Altitude needs access first. An outcome is only ownable if the model can fetch the signal (crash
  reports, metrics, logs), map it to the cause (version → commit), and reproduce and check a fix on
  its own. Name the missing access as part of the rewrite; do not hide it.
- It fits creative work less well. "Go make money" does not work yet; the useful altitude is usually
  one or two levels up, not the top.

## Depth — do it the way the best expert would

- **Instruments, not vocabulary.** Asked to act like an expert, a model often changes its words but
  keeps its methods. Name the expert's actual tools: a database and a statistical model, not a
  markdown table; a profiler trace, not a guess.
- **Raw material.** Start from the rawest source the expert would use (event logs, raw rows, the
  original spec), not a summary someone already digested.
- **Unreasonable targets, stated as reasonable.** If 10 s → 5 s is the ask, ask for 200 ms. When the
  model says it is impossible, say it is solvable and to keep going.
- **Challenge a belief.** Pick one thing taken as true and try to reproduce it from the raw data.
- **New knowledge.** Once deep in the data, ask for a signal nobody knows yet, and prove it on data
  it has not seen.
- **Outside judge.** The model does not grade its own work. Name what else proves the result: a
  test, a benchmark, a held-out dataset, a tool the model can run for immediate feedback.

The four depth questions — answer them before rewriting the request:

1. What would a top professional in this field do here that the request does not ask for?
2. Which raw material would they start from?
3. Which methods and tools would they use?
4. What, other than the model or the requester, would show the result is right?

## Range — methods from other fields

- **Nouns to verbs.** Restate the deliverable as what it must do. "A quarterly deck" becomes "make
  busy people believe a cause-and-effect story and decide under uncertainty in 30 minutes". The verbs
  point at the fields that know how.
- **Pick the crew.** Ask which specialists a team would need if the result had to be excellent.
  Include an adversary: the person paid to find the flaw (a short seller, a forensic accountant, a
  penetration tester).
- **Methods, never voice.** Do not ask the model to write like a short seller. Ask it to do what a
  short seller does to research a position. Role play makes the transcript stranger and the result
  no better.
- The `range-scout` agent in this plugin does this lens in its own context and returns only the
  fields, methods and raw material — use it when the task is big enough to justify a subagent.

## What every lens needs

A computer the model can install software on, and access to the real data (connectors or files).
Without them, altitude and depth fall back to guesses; say so instead of pretending.

## Output

1. The rewritten request, ready to paste.
2. Under it, one line per lens: what it changed, or why it was dropped.
3. The outside judge, named concretely.
4. Any access the rewrite needs that is not there yet.
