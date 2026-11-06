# Future independent proof CI

No active Lean workflow is included in the preparation-only upload, because the
Lake project has not been initialized and no Lean proofs exist.

During Cloud implementation, create `lean.yml` here, using `lean/` as the
working directory and the pinned Lean 4.19.0 / Mathlib v4.19.0 commit specified in
`AGENTS.md`. A real workflow must build the project, check precise paper-facing
theorem types, audit trusted axioms, and check the inventory's coverage statuses.
A final verification workflow must fail on missing or incomplete coverage;
any intermediate development workflow must be clearly labelled work in progress.
Do not use a green placeholder job as evidence of proof verification.
