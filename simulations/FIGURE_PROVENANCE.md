# Figure provenance

| Current item | PDF page | Included assets | Reproduction status / missing resources |
| --- | --- | --- | --- |
| Figure 1, `fig:radial_mixture_two_profile` | 7 | `paper/radial_mixture_with_two_profile_surrogate.pdf`; caption in `paper/comparison_landscape.tex` | Original generator `radial_mixture_with_two_profile_surrogate.py` not found. Random seed, raw eigenvalue data, exact original environment, and surrogate implementation source are unavailable. Numerical reproduction is not established. |
| Figure 2, left panel, `fig:matrix_parameter_sector_geometry` | 15 | `paper/WZ_H.pdf`; `paper/figures/WZ_H.ipe` | Editable Ipe 7.2.28 source present. Export not tested in this preparation session. |
| Figure 2, right panel, same label | 15 | `paper/WZ_big.pdf`; `paper/figures/WZ_big.ipe` | Editable Ipe 7.2.28 source present. Export not tested in this preparation session. |
| Table 1, `tab:comparison_rates` | 7 | `paper/comparison_landscape.tex` | Analytical specializations of the manuscript's theorems; not a simulation. Derivations remain unverified in Lean. |
| Supplementary earlier cone illustration, not in the current PDF | Not applicable | `simulations/illustrations/resolvent_profile_cones.py` | Original script available; imports NumPy and Matplotlib. Syntax checked, not executed. Does not reproduce a current figure. |

Search scope: the source manuscript directory and related subdirectories of the
parent `resolvent/` research directory, plus targeted filename searches in the
broader `local_to_add/` workspace. Scripts and notebooks in sibling regression
and sparse-heavy-tail projects were inspected by filenames/code references and
were not identified as generators of this paper's figures; they are excluded.

A compiled `__pycache__/radial_mixture_with_two_profile_surrogate.cpython-312.pyc`
was present in the source workspace. This is not the missing original source,
was not executed or decompiled, and is excluded from the repository. Ipe
autosaves, duplicate panel PDFs, old manuscript drafts, and private revision
instructions are also excluded.
