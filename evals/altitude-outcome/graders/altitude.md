---
type: llm
---

Pass only if ALL hold:
1. The rewritten request asks for an outcome one level up (for example "keep the CI suite non-flaky" or "drive the flake rate below a target"), not just "fix this test".
2. It names the access the model needs to own that outcome (for example CI run history, the ability to rerun jobs, mapping a failure to a commit, a machine to reproduce on).
3. It names a measure outside the model that shows success (for example a flake rate over N runs, a rerun count).
Fail if it only asks to fix more tests faster.
