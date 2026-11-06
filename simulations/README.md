# Figure sources and reproduction status

The current manuscript has two numbered figures. See `FIGURE_PROVENANCE.md` for
an asset-by-asset record. No raw input dataset was located or selected.

## Published figures

Figure 1 (the radial-mixture histogram, page 7) is available only as
`paper/radial_mixture_with_two_profile_surrogate.pdf`. Its caption gives the
model, dimensions, and repetition count, but the original generator, seed,
raw samples, and original Python environment are missing. Do not present a new
implementation as recovered source or claim that the existing plot has been
numerically reproduced.

Figure 2 (page 15) consists of editable Ipe drawings, not a Monte Carlo
experiment. Ipe 7.2.28 is recorded in both source files. With Ipe and the LaTeX
packages in their embedded preambles installed, these are the intended export
commands, run from `paper/`:

```sh
ipetoipe -pdf -export figures/WZ_H.ipe WZ_H.pdf
ipetoipe -pdf -export figures/WZ_big.ipe WZ_big.pdf
```

Export was not rerun during packaging. The existing panel PDFs are included and
the article build uses them directly.

## Supplementary cone illustration from an earlier draft

`illustrations/resolvent_profile_cones.py` is the original available script,
copied without modification. It draws scalar/compact-set cones that are no
longer included in the current manuscript. It is not the source of the current
matrix-sector panels or radial-mixture histogram.

It imports NumPy and Matplotlib; the original dependency versions are unknown.
`requirements.txt` records these imports, not a tested or locked reproduction
environment. The local packaging environment lacks both packages, so the script
was syntax-checked but not executed and no packages were downloaded.

Example usage in a separate environment, from the repository root:

```sh
python -m venv .venv
. .venv/bin/activate
python -m pip install -r simulations/requirements.txt
mkdir -p simulations/generated/cones
(cd simulations/generated/cones && python ../../illustrations/resolvent_profile_cones.py)
```

The two outputs are `resolvent_profile_cones.pdf` and
`resolvent_profile_cones.png` in `simulations/generated/cones/`. Generated output
is ignored. On Windows use the environment's `Scripts/Activate.ps1` activation
command and run the same script from the chosen output directory.
