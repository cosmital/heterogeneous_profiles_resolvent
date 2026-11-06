# Codex master task: Formal verification of *Resolvent Convergence under Heterogeneous Second-Moment Profiles and Quadratic-Form Control*

## Objective and authority

Create **from scratch**, under this repository's **`lean/` directory, alongside `paper/`**, a fully reproducible Lean 4/Mathlib project formalizing every substantive mathematical result in this paper. The goal is not a demonstration Lean file or a successful build of a small subset: it is a statement-by-statement, kernel-checked formalization of the complete paper, including necessary supporting results from its proofs and appendices.

The paper is **Resolvent Convergence under Heterogeneous Second-Moment Profiles and Quadratic-Form Control**, 62 pages, by Cosme Louart. Read `paper/Resolvent_conv_heterogeneous_profiles_LOUART.pdf` and the accompanying `paper/Resolvent_conv_heterogeneous_profiles.tex` and `paper/comparison_landscape.tex`. These files are already selected; do not substitute an archived draft. **The PDF is authoritative unless an explicitly newer manuscript version is identified.** Never silently substitute the manuscript about scalar monotone operators or its Lean package; this is an independent random-matrix-theory project.

The initial upload/preparation stage must not compile Lean or download Mathlib. The instructions below govern the subsequent Cloud formalization stage, where actual Lean compilation is mandatory. Do not merely draft code or describe what someone else could do. Begin with workspace discovery, a plan tied to the actual results, and implementation of a small compiled foundational module. Continue systematically in dependency order, keeping exact progress and leaving a resumable state between sessions. Never claim the entire paper is verified until every in-scope claim passes the final gates.

## 1. Initialize and pin the independent project under `lean/` in Cloud

1. Use **`paper/`** for the manuscript and **`lean/`** for the independent Lake/Mathlib project. `lean/` currently contains preparation documents only; initialize the actual Lake project there during Cloud implementation. Avoid overwriting unrelated files or depending on `scalar_monotone_verification`.
2. The required target versions are Lean **4.19.0** and Mathlib **v4.19.0**, commit `c44e0c8ee63ca166450922a373c7409c5d26b00b`. Use this pinned pair. No Cloud toolchain availability has been checked during packaging; install or configure these versions during implementation. Any incompatible-version proposal requires explicit author review, not a silent upgrade. Create `lean-toolchain`, `lakefile.toml` (or `lakefile.lean`), and `lake-manifest.json` consistent with these versions; commit their contents. Do not replace the pinned dependency with Mathlib `master` or run uncontrolled dependency upgrades.
3. Initialize a Mathlib-backed Lean library and test it with an actual compiled matrix/complex-number smoke test before developing the paper. Because GitHub release downloads have sometimes failed on this Windows machine, **do not destroy existing valid dependency clones or caches**; diagnose failures and continue using local source builds when appropriate.
4. Confirm and record paths and versions (`lean --version`, `lake --version`, `python --version`; Python is invoked as `python`, not `py -3`). Use explicit working directories for shell operations. The checkout root contains both `paper/` and `lean/`; Lean project commands must run from `lean/`. Do not assume Windows-specific tools are present in Cloud.
5. Set up `AGENTS.md` inside `lean/` and explicitly read it at each new session. Maintain the repository-root `README.md` and add `lean/scripts/`, Lean source modules, `lean/PaperChecks.lean`, and `lean/AxiomAudit.lean`. Maintain documentation under `lean/docs/`. Put CI at the repository root `.github/workflows/lean.yml`, with its working directory set to `lean/`. The initial package has a workflow README only; create active CI after the project exists. Keep mathematical sources under version control and exclude `.lake/`, `.olean` caches, local executables, credentials, and temporary logs.
6. Do not alter the paper's mathematics or source. Any proposed erratum goes into `lean/docs/POTENTIAL_ERRATA.md` for the author to review.

## 2. Make an exhaustive manuscript inventory BEFORE claiming coverage

Read all **62 PDF pages** in order, including the introduction, theorems, examples, equations used as substantive assertions, proofs, appendices, and captions where a mathematical statement is asserted. If a LaTeX source is available, use its labels for stable IDs; cross-check against the PDF, which readers will cite by page/theorem/equation. If only PDF exists, extract its embedded text and confirm symbol-heavy formulas against the rendered pages, especially bars, conjugations, transposes, stars, norm subscripts, exponents, quantifier ranges, and matrix indices. Do not trust OCR or text extraction alone for displayed mathematics.

Produce `lean/docs/PROOF_INDEX.md` and `lean/docs/proof_index.json`, with one row/item for every Theorem, Proposition, Lemma, Corollary, mathematical Remark, substantive Example, and independent key identity. Record:

- exact paper identifier (e.g. Theorem 1.1, Lemma 2.3, Proposition 3.3(ii), equation (3.21), Theorem B.11), PDF page and section;
- the manuscript's full hypotheses and each conclusion, including implicit standing assumptions;
- exact fully qualified Lean declaration name(s), file and source location;
- whether exact, equivalent with proved equivalence, partially proved, not started, or mathematically blocked;
- mathematical scope caveats; compiler status; axiom status; human-reviewed correspondence status.

Do not count `#check` alone or a weaker helper lemma as proof of a paper theorem. Separate a proof for `q=2` from a result for all `q ≥ 2`, and distinguish `z` scalar from general complex matrix parameters `Z`. When the paper has a single result with multiple parts, inventory every part.

## 3. Develop the formalization in mathematical dependency order

Use the actual local Mathlib lemmas when suitable; inspect their source and full types before relying on them. Build general reusable supporting theorems where Mathlib is insufficient, but never take any result of this paper as an axiom. Organize modules approximately as follows (adjust filenames to real dependencies):

**A. Finite-dimensional matrices and complex geometry.** `Matrix/Norms`, `Matrix/PSD`, `Matrix/NumericalRange`, `Sectors`, `ResolventIdentities`: complex and real matrices indexed by `Fin p`, conjugate transpose versus transpose, Loewner order, operator/HS/nuclear norms and duality, trace, numerical range, distances to `[0,∞)`, convex cones and supporting phases, resolvent identities and Sherman–Morrison, Ward inequalities. Include sector bounds for **nonnormal matrix parameters**, not only scalar `z I`.

**B. Deterministic fixed-point theory (Section 2 and Theorems 1.1–1.2).** Formalize in order Lemmas **2.1–2.5**, Proposition **2.6**, Proposition **2.7**, Lemma **2.8**, Proposition **2.9**, Corollary **2.10**, Propositions **2.11–2.12**, Lemma **2.13**, and Theorems **1.1–1.2**. Include existence by Brouwer, exact secant equation (2.12), weighted contraction, uniqueness and stability, holomorphic matrix-parameter dependence via the implicit-function theorem, Stieltjes representations including support on `ℝ₊` and total mass, the matrix-valued measure, and the explicit compact support bound. If a Stieltjes representation theorem is not already in Mathlib, fully formalize the needed general result rather than invoking an unproved claim.

**C. Probability and analytic foundations (Appendix B).** Formalize Theorem **B.1** (replacement/martingale moment inequality) for `1 ≤ q ≤ 2` and `q ≥ 2`, including the complex-valued case; Lemma **B.2** reciprocal differences; Lemmas **B.3–B.4** on complex/conditional quadratic forms; Theorem **B.5** von Bahr–Esseen as used; Propositions **B.6–B.7** finite-moment and truncation estimates; Lemmas **B.8–B.10** test-ball geometry and Gaussian quadratic-form moments; Theorem **B.11** Stieltjes characterization/inversion. Handle real random columns with dependent coordinates, but independent **columns**. Conditional independence and measurability must be formalized when used, not described informally. Retain first-moment arguments even when fourth moments are infinite.

**D. Random resolvents and the two comparison routes (Section 3).** Define the random sample second-moment matrix, `G^Z`, leave-one-out matrices, Schur pivots, conditional expectations, and quadratic-form moduli `M_HS^(q)`, `M_op^(q)`. Prove Proposition **3.1**, Lemma **3.2**, the auxiliary-pivot identities and Proposition **3.3** in both (i) HS and (ii) nuclear norm, including Corollary **3.4**. Complete the HS route: Proposition **3.5**, Lemmas **3.6–3.7**, Proposition **3.8**, and Theorem **1.6**. Complete the operator route: Lemma **3.9**, Proposition **3.10**, Lemma **3.11**, the one-class and conditional statements, Lemma **3.13**, Propositions **3.14–3.16**, and Theorem **1.4**. The **class-by-class replacement** and its varying matrix background are essential; do not substitute an i.i.d. or equal-covariance case.

**E. Resolvent sandwiches and consequences.** Prove Proposition **3.17**, derivative identity (3.65), Corollary **1.7** in both norm routes, and uniform Cauchy-contour transfer. Check the exact conjugation convention for a complex insertion matrix rather than silently omitting a conjugation. Formalize Corollary **1.13** (Marchenko–Pastur under finite variance and uniform integrability), rate claims in Remark **1.14**, and mathematically substantive Examples **1.8–1.12** (including the radial mixture and the growing-trace regime) when asserted as results. Include any necessary ridge-regression identities and explicitly identify which statements are merely illustrative numerical experiments and are not proof obligations.

**F. Remaining substantive claims.** Check notation and supporting identities from the introduction, coefficient properties `τ_Σ`, `σ_Σ`, normalized trace and directional comparisons, appendix statements, and every displayed estimate used as a separate step. Derive table entries from proved theorems where possible. Keep results about asymptotics across dimensions separate from fixed-`p,n` results.

## 4. Translate quantitative statements faithfully

Many results use uniform `O(·)` notation over an index set `Θ ⊆ ℕ²`, compact spectral set `K`, and test matrices. Do **not** formalize `O(·)` as an unexplained constant hidden in each theorem instance, or let constants depend on forbidden variables. Prefer precise explicit finite-dimensional inequalities where possible, then prove the theorem's stated uniform `O` consequence with correct quantifier order.

In particular, constants may depend on the fixed `K`, fixed moment order `q`, and named standing-assumption constants, but not secretly on `p`, `n`, `z∈K`, the deterministic test matrix `A`, or profile quantities explicitly displayed in a bound. Model parameter families and compact-uniform estimates correctly; formalize both `q ≥ 1` and refined `q ≥ 2` regimes. Treat potentially infinite high-order quadratic-form moduli honestly: never assume finite fourth or second moments when a result only requires first moments. Preserve results for arbitrary aspect ratio where the paper claims them and impose the `√p ‖Σ‖_{HS}^∞ = O(n)` condition only on the HS route.

For complex-valued random variables, specify measurable functions and integrals, independent copy constructions, `Lᵖ` norms, conditional expectations, and covariance/second-moment matrices. Preserve **not necessarily centered** columns. Maintain the exact `Σᵢ = E[xᵢ xᵢᵀ]` definition rather than replacing it by centered covariance.

## 5. Build, review, and audit after every increment

For each target theorem:
1. Write a fully elaborated `theorem ... : ... := by` interface matching the paper **before** proving it, with a short comment quoting the paper identifier and meaning.
2. Discover and document existing Mathlib prerequisites; prove any missing lemmas as independent results.
3. Implement a kernel-checked proof, compile the changed module and dependent modules, and repair errors before moving on.
4. Add a reader-facing theorem check in `PaperChecks.lean` that restates the claimed conclusion with its required hypotheses and uses the proved declaration; check any non-obvious equivalence explicitly.
5. Run the axiom audit; require no `sorryAx`, `sorry`, `admit`, `axiom`, `unsafe` proof bypass, inconsistent typeclass assumptions, circular hypotheses, or weakened statement presented as full coverage.
6. Update the exact inventory entry and `lean/docs/PROGRESS.md`, including commands, exit codes, and any mathematical mismatch. A theorem with compile errors or unproved generality remains incomplete.

Use only Lean's usual logical axioms (`propext`, `Classical.choice`, `Quot.sound`) unless a new trusted foundational dependency is explicitly investigated and approved. Do not disable modules or audits to make `lake build` green. A green build verifies **the statements that exist**; it does not establish correspondence with the paper.

Create a command or script that checks all indexed declarations exist and that all inventory items have approved complete-coverage status. Also create actual `lake build`/`lake env lean PaperChecks.lean`/axiom-audit procedures and Windows PowerShell execution instructions. Store generated logs under an ignored `verification/` directory and record the project revision and manuscript hash for each final report.

## 6. Reader-facing final package

Deliver a reproducible independent Lean project under the repository-root `lean/` directory, tracked in the single root Git repository, containing:

- all Lean modules, pin files, library roots, and a final `lake build` that checks the whole development;
- `AGENTS.md`, `README.md`, `LICENSE` or copyright notice as appropriate, and `CITATION.cff`;
- `lean/docs/PROOF_INDEX.md` plus JSON and optionally a searchable HTML table mapping **every paper result and its equation/page number** to exact Lean declarations, proof source locations, assumptions, and status;
- `lean/docs/NOTATION.md` explaining `Σ_i`, `G^Z`, `\widetilde G`, sector constants, `τ_Σ`, `σ_Σ`, `M_{op}^{(q)}`, `M_{HS}^{(q)}`, `L^q`, matrix orders and norms;
- `lean/docs/LOCAL_RUN.md` with native Windows PowerShell commands, installation checks, Mathlib cache alternatives, build commands, how to inspect a single proof in Lean Infoview, and how to run the axiom/coverage audits;
- `lean/docs/MATHLIB_DEPENDENCIES.md` identifying essential external Mathlib theorems used, and `lean/docs/POTENTIAL_ERRATA.md` for genuine mathematical concerns;
- a GitHub Actions workflow that rebuilds and audits the project at pinned versions and fails on incomplete declared coverage (unless a distinct *work-in-progress* workflow is clearly labelled as such).

The preparation-only initial upload is explicitly authorized by the separate upload request. Later formalization sessions must not publish or push additional changes without author authorization. Provide exact commands to reproduce a fresh build. Do not describe incomplete formalization as publication-ready.

## 7. Execution priorities and continuation

This is a substantial 62-page, matrix-valued probability and complex-analysis formalization. **Start implementing rather than producing only a roadmap.** The first independently useful milestone is an actually compiled foundation with numerical-range/sectors, matrix resolvent identities, and the first corresponding paper lemmas. Next formalize the deterministic fixed-point system and its uniqueness; then the analytic/Stieltjes theory and appendices; then the probability and two comparison routes; finally sandwiches, examples, and overall cross-checks. Adjust proof order to real dependencies.

When compilation of a statement fails, repair it, use a different legitimate proof, or record an exact blocker; do not invent a Mathlib theorem. Search for a pre-existing theorem before embarking on a long independent proof. If a manuscript result may be false, produce a minimal counterexample or precise missing hypothesis and flag it for the author; work on unaffected results.

Continue through the inventory in the active session without stopping for routine confirmation. If a session context or execution limit interrupts progress, write `lean/docs/PROGRESS.md` with: last successfully compiled module, exact current compilation error and attempted repairs, last completed paper results, remaining dependencies and next **one concrete theorem**. The next Codex session should resume from this file rather than restarting the project.

**Final completion condition:** a fresh successful `lake build`; passing theorem-type and dependency/axiom checks; no proof placeholders; each in-scope result represented by an exact or proved-equivalent statement; an audited complete proof index tied to the PDF revision; and accurate local/GitHub documentation. Report any remaining human semantic-review step separately from compilation or mathematical incompleteness.

Preparation handoff: no Lean compilation, Mathlib download, or dummy proofs were performed. In the subsequent Cloud formalization task, read `lean/docs/PROGRESS.md`, inspect the initial source inventory and authoritative PDF, initialize the pinned project under `lean/`, and compile the first genuine foundational module. Do not restart manuscript discovery or ask for a project location already specified by this repository.

## 8. Explicit implementation stages and preparation status

The repository preparation stage creates the paper package and unverified source
inventory only. It is not a mathematical verification milestone. The following
implementation stages must each retain exact types, complete hypotheses, actual
compilation, axiom audits, and semantic correspondence review:

1. Initialize the pinned independent Lake project and matrix/complex foundations.
2. Appendix B: probability, moments, conditional reductions, test geometry,
   Gaussian moduli, and Stieltjes characterization; order internal prerequisites
   by their actual dependencies.
3. Section 2: sectors for general complex matrix parameters, deterministic fixed
   points, stability, holomorphy, Stieltjes measures, positivity, support and mass.
4. Section 3.1: probabilistic estimates, leave-one-out identities and auxiliary
   pivots; Section 3.2: full Hilbert--Schmidt route.
5. Section 3.3: full operator route, including class-by-class conditional
   replacement with varying complex matrix backgrounds; Section 3.4: sandwiches.
6. All Section 1 main results, applications, examples, remarks, Table 1,
   mathematical caption claims, asymptotic consequences, and remaining
   substantive identities, followed by a complete source/PDF/Lean coverage audit.

Stages may be interleaved for prerequisites, never omitted. All initial entries
in `lean/docs/proof_index.json` are unverified; their extracted source statements
are not a completed review of implicit hypotheses or multipart coverage.
