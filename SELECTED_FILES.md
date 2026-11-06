# Selected files

Source workspace: the original `resolv_with_codex/` manuscript folder.
Original locations below are relative to that folder; generated documents
have no pre-existing source file. This is a separate clone of the existing
`cosmital/heterogeneous_profiles_resolvent` repository. The original manuscript
and experiment files were copied, not moved or deleted.

Authority: `paper/Resolvent_conv_heterogeneous_profiles_LOUART.pdf` (62 pages).
The selected source is the current manuscript, not an archived draft.
Extracted text before References matches the reference PDF; the current
bibliography regenerates minor metadata/formatting updates and different
reference pagination, as documented in `paper/README.md`.

| Original location | Repository destination | Reason |
| --- | --- | --- |
| `Generated during repository preparation` | `.gitattributes` | Preserve manuscript and figure source bytes while normalizing new documentation. |
| `Generated during repository preparation` | `.github/workflows/README.md` | Reserve the correct root GitHub Actions location without fictitious Lean CI. |
| `Generated during repository preparation` | `.gitignore` | Exclude build products, dependencies, temporary data, caches, and local credentials without excluding figure source scripts. |
| `AGENTS.md (adapted, not copied verbatim)` | `AGENTS.md` | Permanent instructions adapted to paper/ and lean/docs/ while preserving proof and approval requirements. |
| `CODEX_RESOLVENT_LEAN_MASTER_TASK.md (adapted, not copied verbatim)` | `CODEX_RESOLVENT_LEAN_MASTER_TASK.md` | Full original mathematical task adapted for the root repository layout and subsequent Cloud execution; no proof requirements removed. |
| `Generated during repository preparation` | `README.md` | Repository overview, honest build/reproduction status, and Cloud handoff. |
| `Generated during repository preparation` | `SELECTED_FILES.md` | This selection, provenance, exclusions and copied-artifact hash record. |
| `Generated during repository preparation` | `lean/README.md` | Explain intended independent Lean structure, pinned versions, and unstarted status. |
| `Generated during repository preparation` | `lean/docs/NOTATION.md` | Initial mathematical dictionary preserving generality without pretending Lean declarations exist. |
| `Generated during repository preparation` | `lean/docs/POTENTIAL_ERRATA.md` | Separate future mathematical concerns from known packaging and reproduction gaps. |
| `Generated during repository preparation` | `lean/docs/PROGRESS.md` | Precise honest resumable Cloud checkpoint with no claimed formal progress. |
| `Generated during repository preparation` | `lean/docs/PROOF_INDEX.md` | Human-readable initial source inventory; no result marked complete. |
| `Generated during repository preparation` | `lean/docs/proof_index.json` | Machine-readable initial result/equation/caption inventory; every entry explicitly unverified. |
| `Generated during repository preparation` | `paper/README.md` | Identify the authority and preserve working LaTeX paths and build instructions. |
| `Resolvent_conv_heterogeneous_profiles.tex` | `paper/Resolvent_conv_heterogeneous_profiles.tex` | Current manuscript source matching the reference PDF; not an archived draft. |
| `Resolvent_conv_heterogeneous_profiles_LOUART.pdf` | `paper/Resolvent_conv_heterogeneous_profiles_LOUART.pdf` | Authoritative 62-page reference PDF for the formalization. |
| `WZ_H.pdf` | `paper/WZ_H.pdf` | Figure 2 left panel; preserve the relative path used by the manuscript. |
| `WZ_big.pdf` | `paper/WZ_big.pdf` | Figure 2 right panel; preserve the relative path used by the manuscript. |
| `biblio.bib` | `paper/biblio.bib` | Bibliography used by the manuscript. |
| `comparison_landscape.tex` | `paper/comparison_landscape.tex` | Required landscape table and Figure 1 input; restored and matched to the reference PDF. |
| `ejpecp.cls` | `paper/ejpecp.cls` | Required custom EJP/ECP document class, including its existing copyright notices. |
| `figures/WZ_H.ipe` | `paper/figures/WZ_H.ipe` | Editable Ipe 7.2.28 source for Figure 2 left panel. |
| `figures/WZ_big.ipe` | `paper/figures/WZ_big.ipe` | Editable Ipe 7.2.28 source for Figure 2 right panel. |
| `radial_mixture_with_two_profile_surrogate.pdf` | `paper/radial_mixture_with_two_profile_surrogate.pdf` | Figure 1 supplied numerical plot; its generator and raw data are missing. |
| `Generated during repository preparation` | `simulations/FIGURE_PROVENANCE.md` | Precise record of missing radial-mixture resources and available current/archived drawing sources. |
| `Generated during repository preparation` | `simulations/README.md` | Document actual available scripts, dependencies, commands, and limits of numerical reproducibility. |
| `old_or_poubelle/resolvent_profile_cones.py` | `simulations/illustrations/resolvent_profile_cones.py` | Available supplementary cone drawing script from an earlier draft; explicitly not the generator of a current manuscript figure. |
| `Generated during repository preparation` | `simulations/requirements.txt` | Minimal inferred dependencies for the supplied supplementary drawing script. |

## Copied artifact SHA-256 values

| Repository artifact | SHA-256 |
| --- | --- |
| `paper/Resolvent_conv_heterogeneous_profiles.tex` | `db393f557ec0ff3865e1d554f463e253be6905662dd2a1a9a0956efc3a75a67b` |
| `paper/Resolvent_conv_heterogeneous_profiles_LOUART.pdf` | `768e5913ac00e6d7d50f935d1f402e349bd559c3f3a566c0d977b66c5de4c98d` |
| `paper/comparison_landscape.tex` | `7b025df753077ace63e6c37a554ddd64372331a360d799326fa24317bfbd6fa0` |
| `paper/biblio.bib` | `672a4599063fdc10999af25d49d609d260cae3426d415582a2d9b0edffd40b7b` |
| `paper/ejpecp.cls` | `e28acfce618b9f5ec291592082ce850f070e3ae1d35c6ccbe352127347165ed4` |
| `paper/WZ_H.pdf` | `2651c1dd3646eb534b759b5808b3352509360a1dd0570f7728730052f518a483` |
| `paper/WZ_big.pdf` | `654d357eb568b59f3dcbf0e842d33ff19df05b284cc46d4c704324b8275fb0d6` |
| `paper/radial_mixture_with_two_profile_surrogate.pdf` | `571446a9cf79ae509d32b771b0be86ccfc181a65e4caf4b6de683ba8bd726c98` |
| `paper/figures/WZ_H.ipe` | `55db04a21c66d00070a7ef01a22556aede140c4c7c9e5c5ad1b8c90eb1512a48` |
| `paper/figures/WZ_big.ipe` | `f19138e6c03d26dba13f58c3aa83445b5c85b810bf54cd62ecd64d87e1c8e82c` |
| `simulations/illustrations/resolvent_profile_cones.py` | `c93139f29de2df9b89eea616a1ebc35d2d0f69f2c793cc8657ebd70137b1c304` |

## Intentional exclusions and missing resources

- Old manuscripts, revision instructions, audit/conversation notes, and the upload instruction itself are not research artifacts selected for publication.
- Current build auxiliaries, editor autosaves, `.pyc` caches, local configuration/credentials, downloaded libraries, and unrelated parent/sibling projects are excluded.
- The source workspace `.git` marker contains no valid Git metadata; it was not initialized, replaced, moved or copied. Separate valid Git boundaries were found in sibling projects and left untouched.
- Duplicate `figures/WZ_H.pdf` and `figures/WZ_big.pdf` are byte-identical to the selected root panel PDFs and are omitted as duplicates.
- The just-rebuilt `Resolvent_conv_heterogeneous_profiles.pdf` is not duplicated in the repository: the preferred authoritative `_LOUART.pdf` is included, and the build produces the unadorned filename.
- Figure 1 original numerical source, random seed, raw data and original dependency versions are missing. No replacement script was invented. See `simulations/FIGURE_PROVENANCE.md`.
- The only supplied Python source is an earlier supplementary cone illustration. It is explicitly not a current figure generator. Its dependencies are inferred, not a recovered environment.
- No large input datasets or downloaded dependencies are included. All selected artifacts are below GitHub standard per-file size limits.
- Lean source proofs, manifests and active CI have not been fabricated; Cloud initialization and all proof work remain to be done.
