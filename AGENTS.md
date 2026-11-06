# AGENTS.md — Resolvent profiles Lean verification

This repository formally verifies **Resolvent Convergence under Heterogeneous Second-Moment Profiles and Quadratic-Form Control**. The mathematical authority is `paper/Resolvent_conv_heterogeneous_profiles_LOUART.pdf` (62 pages), with its accompanying LaTeX source and `paper/comparison_landscape.tex`, unless the author explicitly supersedes it.

- Develop in the `lean/` project using pinned Lean 4.19.0 and Mathlib v4.19.0; never silently upgrade dependencies.
- Do not alter the paper, introduce `sorry`, `admit`, new `axiom`s, `unsafe` proof bypasses, or hide a result in assumptions.
- Preserve all quantifiers and standing assumptions, especially independence across columns only, noncentered data, general complex matrix parameter Z, and uniformity of O constants.
- Check full matrix norms, conjugate transpose, sector conditions, domain/support, positivity, moment finiteness, measurability, and conditional independence.
- Compile each changed module and its dependents. Audit every final declaration for trusted axioms and verify the precise type against the paper.
- Maintain `lean/docs/PROOF_INDEX.md`, `lean/docs/proof_index.json`, `lean/docs/PROGRESS.md`, and `lean/docs/POTENTIAL_ERRATA.md`; do not mark items complete unless proof and mathematical correspondence both check.
- Never modify user paper sources or publish/push to GitHub without approval.
- For each session: read `lean/docs/PROGRESS.md`, work on the next explicit dependency, build, update documentation, and leave a precise resumable checkpoint.

## Repository layout and preparation boundary

- The Git repository root contains `paper/`, `simulations/`, and `lean/`. Keep one
  root Git repository; the Lean package is independent of other mathematical
  projects, not a nested Git repository.
- The initial upload is a preparation-only milestone. Do not compile Lean,
  initialize/download Mathlib, or create dummy proof files during that milestone.
  Formalization has not started and every inventory item is unverified.
- In a subsequent Cloud formalization task, initialize the actual Lake project,
  pin Lean `4.19.0` and Mathlib `v4.19.0` at
  `c44e0c8ee63ca166450922a373c7409c5d26b00b`, and then perform all compilation,
  precise-type checks, and axiom audits required above. Never silently upgrade.
- Formalize from scratch and cover the complete manuscript: foundations,
  Appendix B, Section 2, Sections 3.1, 3.2, 3.3, 3.4, applications and remaining
  substantive identities, examples, remarks, table/caption claims.
- Treat the initial inventory as a starting source inventory, not an exhaustive
  semantic audit. Split multipart claims, record all standing hypotheses, and
  inspect all PDF pages before claiming coverage. Do not weaken statements or
  hide target results in assumptions.
- Read `lean/docs/PROGRESS.md` first in each formalization session. Keep
  `lean/docs/PROOF_INDEX.md`, `lean/docs/proof_index.json`, `lean/docs/NOTATION.md`,
  `lean/docs/POTENTIAL_ERRATA.md`, and progress current.
- Do not change paper sources to make proofs pass. Record suspected issues for
  author review, preserving their status as suspected until reviewed.
- Never imply that compilation alone proves mathematical correspondence or
  completeness. The initial package has no compiled Lean declarations or CI.
- The initial repository upload was explicitly authorized by the author through
  `instruction_to_upload_to_github.md`; this does not authorize later unrelated
  publication, visibility changes, or history rewrites.
