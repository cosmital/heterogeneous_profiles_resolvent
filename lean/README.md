# Future independent Lean project

Mathematical formalization has not started. This directory contains planning and
source-inventory documentation only. There are no Lean proofs, no Lake project,
no dependency downloads, no local compilation, and no passing proof CI.

Required pins for Cloud initialization:

- Lean 4.19.0 (`leanprover/lean4:v4.19.0`).
- Mathlib v4.19.0, commit `c44e0c8ee63ca166450922a373c7409c5d26b00b`.

Start with the root `AGENTS.md`, `CODEX_RESOLVENT_LEAN_MASTER_TASK.md`, and
`docs/PROGRESS.md`. Initialize a Lake library here with genuine source modules,
`lean-toolchain`, `lakefile.toml` or `lakefile.lean`, a resolved pinned
`lake-manifest.json`, `PaperChecks.lean`, and `AxiomAudit.lean`. Do not fabricate
proof stubs or a dependency manifest and call them validated. Keep the single
Git repository at its existing root; do not run `git init` here.

Intended modules cover matrix norms/PSD/numerical ranges, sectors and resolvent
identities, Appendix B foundations, deterministic fixed points (Section 2),
probabilistic estimates and both comparison routes (Sections 3.1–3.3),
sandwiches (Section 3.4), and applications. All quantitative statements must
retain their full uniformity and generality. Read the master task for details.

After initialization, future validation must include `lake build`, precise
paper theorem checks, trusted-axiom audits, and complete inventory review.
These commands have not been run during repository preparation.
