# Heterogeneous profiles: resolvent convergence

Research material for **Resolvent Convergence under Heterogeneous Second-Moment
Profiles and Quadratic-Form Control**, by Cosme Louart.

- `paper/` contains the current LaTeX manuscript, the authoritative
  [`Resolvent_conv_heterogeneous_profiles_LOUART.pdf`](paper/Resolvent_conv_heterogeneous_profiles_LOUART.pdf),
  bibliography, document class, figure PDFs, and available Ipe sources.
- `simulations/` documents figure provenance and missing reproduction resources,
  and includes one supplementary Python illustration from an earlier draft.
- `lean/` is reserved for a new, independent Lean 4/Mathlib formalization.
  **Mathematical formalization has not started; no result is verified.**
- `AGENTS.md` and `CODEX_RESOLVENT_LEAN_MASTER_TASK.md` give permanent proof
  requirements and the staged formalization task.
- `.github/workflows/README.md` describes future CI requirements. There is no
  active Lean workflow or passing Lean build at this preparation stage.

## Build the article

Install a LaTeX distribution providing PDFLaTeX, BibTeX, and `latexmk`, including
AMS packages, `mathrsfs`, `adjustbox`, `array`, `longtable`, `multirow`,
`arydshln`, `pdflscape`, `afterpage`, and `capt-of`. The custom `ejpecp.cls` is
included. From this repository:

```sh
cd paper
latexmk -pdf -interaction=nonstopmode -halt-on-error -file-line-error Resolvent_conv_heterogeneous_profiles.tex
```

This produces `paper/Resolvent_conv_heterogeneous_profiles.pdf`; the separately
named `..._LOUART.pdf` remains the reference version. Keep
`comparison_landscape.tex` beside the main source. No path outside `paper/` is
needed. The source version was already successfully built before packaging;
see `paper/README.md` for the packaged-build validation record.

## Figures and numerical experiments

See [`simulations/README.md`](simulations/README.md) and
[`simulations/FIGURE_PROVENANCE.md`](simulations/FIGURE_PROVENANCE.md).
The published radial-mixture histogram is supplied as a PDF, but its original
Python source, random seed, sampled data, and original dependency versions were
not found. **Numerical reproduction of that figure is not established.** The
sector drawings have Ipe sources. The archived cone script is supplementary and
does not reproduce either current manuscript figure.

## Formalization handoff

Read `AGENTS.md`, the master task, and `lean/docs/PROGRESS.md`. The intended pins
are Lean **4.19.0** and Mathlib **v4.19.0**, commit
`c44e0c8ee63ca166450922a373c7409c5d26b00b`.
No Lean compilation or Mathlib download was performed during preparation.
The Cloud implementation must initialize the Lake project, resolve its pinned
manifest, and implement and compile real proofs; a README or inventory does not
constitute verification. Initial inventory entries are all unverified and need
semantic review and decomposition before coverage can be claimed.

`SELECTED_FILES.md` records file provenance, selection, exclusions, and hashes of
copied artifacts. No new license for the author's manuscript or code is assigned
by this upload; existing notices in supplied files are retained.
