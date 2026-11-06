# Formalization progress

## 2026-11-06 — Preparation only

- Mathematical formalization: **not started**.
- Verified paper results: **none**. Compiled Lean modules: **none**.
- Lean compilation: **not performed**. Mathlib downloads: **not performed**.
- Lake project, dependency lockfile, proof/type-check modules, axiom-audit code,
  and active Lean CI: **not initialized**.
- The selected 62-page reference PDF, matching LaTeX inputs, bibliography, custom
  class, and available figure sources are under `paper/`.
- `PROOF_INDEX.md` and `proof_index.json` are initial source inventories. Every
  item is unverified. Environment/label extraction is not a semantic coverage
  audit; split multipart conclusions, inspect implicit assumptions and all PDF
  pages, and add unlabelled substantive assertions before claiming completeness.
- Required pins: Lean 4.19.0; Mathlib v4.19.0 at
  `c44e0c8ee63ca166450922a373c7409c5d26b00b`.
- Numerical reproducibility gap: original Figure 1 simulation source, seed, data,
  and exact environment are missing. See `../../simulations/FIGURE_PROVENANCE.md`.
  This is separate from proving the mathematical radial-mixture example.

## Next concrete dependency in Cloud

Initialize the independent Lake project in `lean/` at the pinned versions,
record the actual toolchain, and compile one genuine foundational matrix lemma:
for a positive-semidefinite Hermitian matrix, its quadratic form has
nonnegative real part and zero imaginary part. Inspect the exact Mathlib
matrix/PSD definitions before choosing a declaration and prove the precise
interface required for sectorial resolvent calculus. This lemma is a foundation,
not completion of Lemma 2.1 or another paper result.

Then develop numerical-range and supporting-phase prerequisites for Section 2,
interleaving Appendix B prerequisites where needed. Resume by reading this
file, not by replacing the manuscript or importing an unrelated Lean project.
Any mathematical issue must be logged in `POTENTIAL_ERRATA.md` for author review.
