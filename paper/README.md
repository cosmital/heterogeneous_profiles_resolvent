# Manuscript source and authority

The authoritative manuscript is `Resolvent_conv_heterogeneous_profiles_LOUART.pdf`
(62 pages), with source `Resolvent_conv_heterogeneous_profiles.tex` and the
required `comparison_landscape.tex`. The source file is the current workspace
version, not a copy from `old_version/` or `messages_to_codex_old/`.

The landscape input was restored during the preceding LaTeX repair; its page 7
rendering matched the existing reference PDF. The complete source was rebuilt
successfully before this repository was prepared. The reference PDF is preserved
byte for byte. PDF extraction is used only as a correspondence cross-check;
symbol-heavy statements still require visual inspection during formalization.

Correspondence check: extracted text before the References section is identical
between the reference PDF and the current workspace rebuild. The current
`biblio.bib` regenerates slightly updated reference entries (capitalization,
edition formatting, and arXiv metadata) and reference pagination. Therefore a
fresh build is not byte-identical to the reference PDF; the reference PDF is
retained as the mathematical authority. No older bibliography or manuscript
was substituted to hide these differences.

Build from this directory:

```sh
latexmk -pdf -interaction=nonstopmode -halt-on-error -file-line-error Resolvent_conv_heterogeneous_profiles.tex
```

All non-system inputs are supplied locally. `WZ_H.pdf`, `WZ_big.pdf`, and the
radial-mixture plot intentionally remain next to the main source to preserve
its figure paths. The duplicate copies of `WZ_H.pdf` and `WZ_big.pdf` in the
original `figures/` directory were identical and are not duplicated here.
The corresponding editable `.ipe` files are under `figures/`.

Packaged-build validation (2026-11-06): the command above succeeded with exit 0
using PDFLaTeX/BibTeX from TeX Live 2023 and latexmk 4.83, producing 62 pages.
The final log has no errors, undefined references/citations, or rerun requests.
The remaining diagnostics are the class's repeated `pagebackref` option,
two small overfull horizontal boxes, and one underfull vertical box.
The generated unadorned PDF and all build auxiliaries are ignored; the
authoritative `_LOUART.pdf` is unchanged and tracked. No Lean compilation or
dependency download was performed.
