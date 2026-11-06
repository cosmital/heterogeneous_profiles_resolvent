# Paper-to-Lean notation dictionary (initial)

No Lean identifiers have been assigned or compiled. The choices below are
requirements for the future definitions, not existing declarations.

| Paper notation | Meaning and translation requirement |
| --- | --- |
| (p,n), (Theta) | Positive dimensions and a dimension-indexed family; preserve every uniform quantifier. |
| (X=(x_1,ldots,x_n)) | Real random columns, independent across columns only, with finite second moments; coordinates may be dependent. |
| (Sigma_i=mathbb E[x_i x_i^	op]) | Uncentered second-moment matrix; do not replace by centered covariance. |
| (M^	op,M^*) | Transpose and conjugate transpose; distinguish them for complex matrices. |
| (Re M,Im M) | Hermitian real and imaginary parts, not entrywise real/imaginary parts. |
| (mathcal W(Z)) | Full complex numerical range; general nonnormal complex (Z) is allowed. |
| (eta_Z,mathcal C_Z,omega_Z,c_Z) | Numerical-range distance, sector, bisecting unit phase and coercivity constant as defined in Section 2. |
| (mathbb R_+,Omega) | ([0,infty)) and its complex complement; retain domain and support restrictions. |
| (G^z,G^Z) | Random sample second-moment resolvents, with scalar or general matrix spectral parameter. |
| (widetilde G^z,widetilde G^Z,widetildeGamma) | Deterministic fixed-point resolvents and diagonal companion parameters. |
| (G_D^Z,r(D)) | Auxiliary resolvent and exact inverse defect; preserve weights in transfer inequalities. |
| (|A|_{
m op},|A|_{
m HS},|A|_*) | Full operator, Hilbert–Schmidt, and nuclear norms and their dualities. |
| (M_{
m op}^{(q)},M_{
m HS}^{(q)}) | Quadratic-form moduli with deterministic real symmetric tests in the specified unit balls; keep finite-moment hypotheses exact. |
| (|cdot|_{L^q}) | Measurable complex random-variable moment norm, with correct integrability and conditional structure. |
| (	au_Sigma) | Operator-route class-proportion/profile-size coefficient. |
| (sigma_Sigma) | Infimum over commuting PSD approximants of span dimension times approximation factor. |
| (Apreceq B) | Hermitian Loewner order via all complex-vector quadratic forms. |
| (mathcal S^z,widetilde{mathcal S}^{,z}) | Random and deterministic sandwiches/linear response; audit conjugation for complex insertions. |
| (widetildemu,widetildemu_i) | Positive measures with stated mass and support, not just formal transforms. |
| (O(cdot)) | Explicit inequalities or correctly quantified uniform estimates. Constants may depend only on named fixed parameters, not dimensions, tests or displayed profile factors. |

Standing conventions are in `paper/Resolvent_conv_heterogeneous_profiles.tex`,
lines 169–233 and 332–342; Section 3 adds its fixed common-sector assumptions.
Consult the authoritative PDF and the complete source context when translating.
