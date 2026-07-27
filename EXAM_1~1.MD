# 10 — Revision log: official Spring 2026 announcement

**Trigger.** Prof. Oren Louidor (course coordinator, and the author of the Spring 2026 exam) issued an official announcement specifying the exam format and a list of excluded topics. All nine deliverables were revised in place against it.

**The announcement, as applied**

- **Format, Moed A and Moed B:** 4 open questions · 5 subparts each · subparts increasing in difficulty · 5 points per subpart · 100 points. *(16 multiple-choice questions apply only to the special moed.)*
- **Excluded:** moment generating functions · simulation · couplings · Poisson processes · the relationship between the Poisson and Gamma distributions · the Beta distribution · the Chernoff bound · the multivariate normal distribution · almost-sure convergence · Borel–Cantelli lemmas.
- **Everything else taught in a lecture or tutorial is examinable.**

---

## 1. Every conclusion that changed

| # | Previous conclusion | Revised conclusion | Where |
|---|---|---|---|
| 1 | "The exam format is settled: four open questions × five subparts — *inferred* from the 2023–2024 papers." | **Officially confirmed**, not inferred. Also newly established: subparts *increase in difficulty* by design, and each is worth exactly 5 points. The multiple-choice papers are demoted from "format practice" to "construction bank only". | `04` §1, `06` header, `07` header, `09` §0 |
| 2 | **"MGFs are the highest-priority gap: in the syllabus, in Raviv's notes, in six of Louidor's exams — and in no tutorial this semester."** | **Withdrawn and reversed.** MGFs are officially excluded. This was not a gap; it was out-of-scope material that recent-exam frequency made look urgent. Removed from every priority list, diagnostic, representative set and study recommendation. | `02` F32, `03` Part 3, `04` §2.8, `06`, `08`, `09` §2 and §5 |
| 3 | **"Poisson splitting drives question 4 of both 2024 papers — practise the total-probability derivation so you are safe either way."** | **Withdrawn.** Poisson processes are excluded outright. The suggested workaround (derive it rather than quote it) was wrong: the *setting* is excluded, not merely the theorem. Only genuinely isolable subparts are retained, and only as drills. | `03` Part 3, `04` §2.4, `06`, `07` appendix, `09` §7 |
| 4 | "Order statistics is a coverage gap flagged for caution." | Still not a named syllabus topic, but fully derivable from item 12 + independence, both examinable, and it touches nothing on the exclusion list. **Reclassified from 'flagged' to 'examinable, in Core'.** | `03` Family F, `09` §5 |
| 5 | "Borel–Cantelli and Chernoff: skim the statement only (absent from Raviv's notes)." | **Confirmed by the announcement** — both officially excluded. My inference from their absence in Raviv's notes was correct. Now stated as fact, and they no longer appear as anything to skim. | `03` Part 3, `09` §5 |
| 6 | "Conditional variance / EVE law: Moderate priority — learn it, a first appearance is plausible." | **Promoted to High.** With MGFs and Poisson processes removed, this is now the most prominent topic that is taught (T7, Raviv §10.5) and examinable but has **no precedent anywhere in the exam bank**. Given a dedicated repair item and a constructed diagnostic. | `02` F29, `09` §2 item 6, §5, `08` |
| 7 | "The Gamma family is Strong and recurring." | **Retained, with a precise carve-out.** The Gamma *distribution* remains examinable. Only the **Poisson–Gamma relationship** is excluded (the duality and the Poisson-conditional-on-Gamma conjugacy of 2018wA Q14/Q15). The exponential→Gamma convolution used in 2023spB Q2 and c2adcfa6 Q2 is a different result and stays. | `02` F22, `03` Family B, `04` §3, `06` C10 |
| 8 | "Sums of independent normals and joint normality (Family K) — in Core." | **Split.** Univariate sums, variances and covariance-by-shared-components remain examinable. Writing a **joint/bivariate normal with a covariance matrix is excluded.** Family K reclassified as *Mixed*. | `03` Part 2, `04` §2.2, `07` Procedure K step 5 |
| 9 | "Strong law of large numbers: low priority (not in the syllabus list)." | **Confirmed excluded** — almost-sure convergence is on the official list. Convergence *in probability* and the weak law are unaffected, so every convergence question in the bank survives. | `03` Family H, `09` §7 |
| 10 | "Multinomial is drilled more than the exams warrant, but cheap to keep." | **Further demoted.** Its principal exam role was as the fallback route inside Poisson-splitting questions, which are excluded. T5 drops to priority 5. | `02` F43, `05`, `09` §3 |
| 11 | "The answer-format rule allows a PMF, density, CDF, MGF, or name+parameters." | The **MGF option is no longer available to you**, even though it appears in the older papers' instructions and in the distribution sheet's MGF column. | `02` F46, `04` §10, `07` Procedure 0 |
| 12 | "Family D (joint continuous densities) is Critical — in Core." | **Unchanged in status, but a real defect was exposed and fixed.** Family D was Critical yet had **no Core representative**, because the open-format papers contain no pure Family D question. Removing 2024wB Q4 forced a re-audit that surfaced this. A composite drill (**V4**) now fills the slot. | `03` Family D, `06` V4 |

---

## 2. Every functionality removed or downgraded

**Removed from the current priority ranking (retained in the historical inventory, marked `Excluded from Spring 2026 exam`):**

| ID | Functionality | Previous priority | Reason |
|---|---|---|---|
| **F31** | Poisson splitting / thinning | **Critical** | Poisson processes excluded |
| **F32** | MGF identification | **High** | MGFs excluded |

**Downgraded:**

| ID | Functionality | Change | Reason |
|---|---|---|---|
| F30 | Wald / random sums | Critical → **High** | Its best specimen (2024wA Q4a) now sits inside an otherwise excluded question, so coverage is thin. Still syllabus item 18 |
| F43 | Multinomial | High → **Moderate** | Its exam role was the fallback route inside excluded splitting questions |

**Partially restricted (examinable, with a named carve-out):**

| ID | Functionality | Carve-out |
|---|---|---|
| F26 | Sums of independent normals | Univariate sums and linear combinations remain examinable. "A linear image of a normal *vector* is jointly normal", and writing a 2×2 covariance matrix, are **excluded** |
| F36 | Convergence | Convergence **in probability** (weak) is examinable. **Almost-sure** convergence and the strong law are excluded |
| F46 | Answer-format rule | PMF, density, CDF or name+parameters. **The MGF option is gone** |

**Promoted:**

| ID | Functionality | Change | Reason |
|---|---|---|---|
| F06 | Continuous total probability | → **Critical, top-5** | Now the general route to results that used to be quoted via splitting |
| F08 | Continuous Bayes / density given an event | → **Critical, top-5** | Carried by both C6 and C8 |
| F20 | Marginal by integrating out | → **Critical** | The main route in the replacement Core question |
| F24 | Non-monotone transformation | → **High**, with a mandatory Extra item | No tutorial drills it; Louidor sets it regularly |
| F29 | Conditional variance / EVE law | Moderate → **High** | Taught and examinable with zero exam precedent — see §1 row 6 |

**Added (isolated while validating the replacement Core question):**

| ID | Functionality | Priority |
|---|---|---|
| **F47** | Complete the square inside a normal integral | High |
| **F48** | Conditional independence given a latent variable | High |

**Net:** 46 functionalities → 48. Of these, **46 examinable** (23 Critical, 19 High, 4 Moderate) and **2 marked excluded**.

---

## 3. Every representative question removed, or reduced to selected subparts

### Removed in full

| Question | Was | Excluded topic |
|---|---|---|
| **2024wB Q4 (a–e)** — Poisson points in the unit disc | **Core C6** | Poisson processes |
| **2021spA Q4** — MGF as a mixture of two Poissons | Extra E4 | MGFs |
| 2021spB Q4 · 2017spB Q5 · 2019spA Q3 · 2019spB Q13 · c2adcfa6 Q4 | Redundant list | Poisson processes |
| 2019spA Q10 · 2019spB Q5 · 2020spB-sol Q1′ · 2020spA-sol Q10 · 8598-sol Q9 · 2017spB MGF item | Redundant list | MGFs |
| c2adcfa6 Q7 · 8598-sol Q16 · 2017spB Q13 | Redundant list | Multivariate normal |
| 2018wA Q14, Q15 | Redundant list | Poisson–Gamma relationship |
| 6637-sol ת'Q5 | Redundant list | Beta distribution |

### Reduced to selected subparts

| Question | Solve | Skip | Excluded element |
|---|---|---|---|
| **2023spA Q4** (Core **C9**) | (a) (b) (c) (e) | **(d)** | "Find the **joint distribution** of `X_i` and `X_j`" — a bivariate normal with a 2×2 covariance matrix. **Multivariate normal excluded.** Four of five subparts survive, so the question stays in Core |
| **2024wA Q4** | **(a) only, as a 5-minute drill — not selected as a question** | (b) (c) (d) (e) | Subparts (b)–(e) build a Poisson process over sub-intervals. Subpart (a) is a clean Wald / random-sum exercise, genuinely isolable, so it is retained *only* as a targeted drill. Per your instruction, a full question is not selected when only one subpart is relevant |
| **2024wA** as a timed mock | Q1, Q2, Q3 in 2h15 | Q4 | Same reason |

---

## 4. Replacement question added

### **C6 (new) — 2023spB Q4 (a–e) · "a factory makes machines that make bolts"** (`a1e1cda2`)

**Setup.** `X ~ N(0,1)` is the length the machine is calibrated to. Given `X = x`, the bolts `Y_1, Y_2, …` are iid `N(x, 1)`.
(a) `E[Y_1]` · (b) the density `f_{Y_1}(y)` · (c) the conditional density `f_{X|Y_1}(x|y)` · (d) `E(X | Y_1 = y)` · (e) `E(Y_2 | Y_1 = y)`, with proof.

**Why this one.** Removing 2024wB Q4 left the Core set without a question that (i) obtains a marginal density by integrating a conditional against a prior, and (ii) produces a full posterior density and then smooths over it. 2023spB Q4 does both, in the officially confirmed 5-subpart shape, from a Moed B paper, with a complete typed official solution. No other question in the folder covers this without duplicating an existing Core item.

**Exclusion check performed.** This is a hierarchical **univariate** normal model. The joint law of `Y_1,…,Y_n` given `X` is handed to you as an explicit **product of independent univariate normals**, and Louidor's own solution obtains the marginal by **completing the square**, not by invoking a normal vector or a covariance matrix. It never names or uses the multivariate normal distribution. No MGF, no Poisson, no Gamma, no Beta appears anywhere in the question or its solution. **Clear.**

**Functionalities it restores or adds:** F06, F08, F20, F21, F28, and the two new items **F47** (completing the square) and **F48** (conditional independence given a latent variable).

**Bonus property.** Its answers are interpretable and therefore self-checking: `Y_1 ~ N(0,2)` (variance 1 from calibration + 1 from the machine); `X | Y_1=y ~ N(y/2, 1/2)` (the posterior mean shrinks the observation halfway to the prior); `E(Y_2|Y_1=y) = y/2` (predict the next bolt through the posterior on the machine, not from the observation directly). Nothing else in the bank rewards a sanity check this directly.

### Secondary additions covering functionality lost with 2024wB Q4

| New item | Set | Covers |
|---|---|---|
| **V4** — composite Family D drill: 2020spA-sol Q12 (`P(2X<Y)`) + c2adcfa6 Q1 (uniform on a triangle) + 2018wA Q3 (`Cov(4X,Y)`) | Variation | F18, F19, F16 — drawing a 2-D support and splitting double-integral limits. Family D was Critical with no Core carrier; the open-format papers contain no pure Family D question, so a composite is the only honest option |
| **E6** — 2021spB Q1 (toy thrown in a square room) | Extra | Geometric probability as an area ratio, then `Geo(p)` and memorylessness. Restores the area-ratio content lost with 2024wB Q4a |
| **E4 promoted to mandatory** — 2018wA Q7 | Extra | F24 non-monotone transformation. It replaced the deleted MGF item in the Extra slot |
| **Constructed EVE-law exercise** — compute `Var(Y_1)` in C6 two ways | Diagnostic | F29. Necessary because no exam in the bank uses the EVE law as a main step |

---

## 5. The revised Core set

| # | Question | Source | Spring 2026 status | Solve | Skip |
|---|---|---|---|---|---|
| **C1** | 2024wA Q1 — binary vectors as matrix rows | `df62117f` | Examinable | a b c d e | — |
| **C2** | 2024wA Q2 — moments of the standard normal | `df62117f` | Examinable | a b c d e | — |
| **C3** | 2024wB Q1 — max and min of n dice | `83f1db1c` | Examinable | a b c d e | — |
| **C4** | 2024wB Q2 — sum, difference, mod-1 of uniforms | `83f1db1c` | Examinable | a b c d e | — |
| **C5** | 2024wB Q3 — balls repainted white | `83f1db1c` | Examinable | a b c d e | — |
| **C6** | **2023spB Q4 — machine that makes bolts** ★ replacement | `a1e1cda2` | Examinable | a b c d e | — |
| **C7** | 2023spA Q2 — boys not chosen at the dance | `769b5b18` | Examinable | a b c d e | — |
| **C8** | 2023spA Q3 — `U ~ Unif[1,2]`, `T\|U ~ Exp(U)` | `769b5b18` | Examinable | a b c d e | — |
| **C9** | 2023spA Q4 — weighted tree with N(0,1) edges | `769b5b18` | **Mixed question** | a b c **e** | **(d)** — bivariate normal |
| **C10** | 2023spB Q2 — estimating an exponential rate by 1/X̄ | `a1e1cda2` | Examinable | a b c d e | — |

**Totals:** 10 questions · 50 subparts · **49 to solve, 1 to skip.**

**Provenance:** 5 from Winter 2024 (the two most recent papers), 5 from Spring 2023. Two from Moed A papers, two from Moed B papers, and all four of the modern open-format exams are represented.

---

## 6. Uncertainty about reliance on excluded topics

### Resolved with confidence

| Question | Concern | Resolution |
|---|---|---|
| C2 (2024wA Q2) | Normal moments — does it use an MGF? | **No.** Direct integration and integration by parts throughout; the MGF is never mentioned. Clear |
| C10 (2023spB Q2) | Gamma-heavy — Poisson–Gamma? | **No.** Poisson never appears. `X̄ ~ Gamma(n, nλ)` comes from the exponential→Gamma convolution, and the exam **supplies the Gamma density in the hint**. Clear |
| C6 (2023spB Q4) | Two normals — multivariate normal? | **No.** Explicit product of independent univariate normals; the official solution completes the square rather than invoking a vector. Clear |
| C8 (2023spA Q3) | Exponential conditional law — Poisson process? | **No.** No counting process, no arrival times, no Poisson-distributed count. Clear |
| C7, C10 | Convergence — almost-sure? | **No.** Both prove convergence **in probability** via Chebyshev. Clear |
| C3 (2024wB Q1) | Order statistics not in the syllabus? | Not on the exclusion list, and fully derivable from item 12 + independence. Clear |
| E1 (2024wA Q3) | Exponential backoff — Poisson process? | **No.** Independent exponential waiting times with no counting process. Clear |
| C9 (2023spA Q4) | Bivariate normal | **Confirmed present in subpart (d) only.** (a),(b),(c),(e) are univariate. Subpart (d) is skipped |

### Genuinely unresolved — flagged, and none affects the plan

| Item | Uncertainty | Impact |
|---|---|---|
| **2018wA Q12** (time between women / between men entering a shop) | Is this a Poisson process, or merely competing exponentials? The phrasing "the time between entries is exponential" is process language, but the computation is a `min` of independents | **None.** Redundant-set multiple-choice item, not selected. Marked *Requires inspection* in `01` |
| **8598-sol Q4** (a Poisson mixture) | Whether the construction counts as a process | **None.** Redundant-set item, orphan solution with no matching paper. Marked *Requires inspection* |
| **c2adcfa6 Q8** (estimating a mean by repeated sampling) | The framing edges toward "simulation", which is excluded | **None.** Redundant-set item. Marked *Requires inspection* |
| **c2adcfa6 Q4** (families arriving at a restaurant, Poisson count, random sizes) | A compound sum with a Poisson count — arguably a random sum (examinable) rather than a process | Marked **Partially relevant**. Not selected; C6 and the Q4(a) drill cover random sums |
| **2021spB Q4** route ב' | Route א' (splitting) is excluded; route ב' (condition on `N`, multinomial, smoothing) is examinable on its own | Marked **Partially relevant**. Not selected — it adds nothing over C1 and V5 |
| **T10** (`e8f2b111`) | Headed **חורף תשפ"ד**, not תשפ"ו — reused material from a previous semester | Its content is examinable, but **confirm with the lecturer that it was actually taught this semester**. Flagged in `01`, `05` and `09` §3 |
| **`24e7d8a5`** (Louidor's own 2022 lecture notes) | Contains excluded material (2-D Jacobians, MGFs) | Marked *Requires inspection*. Use for phrasing only, never for scope. Raviv's notes plus the announcement define scope |

**No Core question carries unresolved exclusion risk.**

---

## 7. Final verification of the revised Core set

Each of the ten Core questions checked line by line against all ten excluded topics.

| Core | MGF | Simul. | Coupl. | Poisson proc. | Pois–Gamma | Beta | Chernoff | Multivar. normal | a.s. conv. | Borel–Cantelli |
|---|---|---|---|---|---|---|---|---|---|---|
| C1 2024wA Q1 | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| C2 2024wA Q2 | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| C3 2024wB Q1 | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| C4 2024wB Q2 | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| C5 2024wB Q3 | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| C6 2023spB Q4 | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| C7 2023spA Q2 | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| C8 2023spA Q3 | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| C9 2023spA Q4 (a,b,c,e) | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ *(d excluded and skipped)* | ✓ | ✓ |
| C10 2023spB Q2 | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |

✓ = free of that excluded topic. **The revised Core set is clear of all ten exclusions.**

### Automated cross-checks run over the revised files

- Every `F##` identifier cited in `03`, `06`, `07`, `08` and `09` exists in `02_functionality_map.csv` — **no dangling references.**
- Every 8-character file stub cited across all ten deliverables corresponds to a real PDF in the knowledge folder — **no phantom citations.**
- All four CSVs parse with a uniform column count.
- No diagnostic in `08_diagnostic.csv` names an excluded topic.
- Every Critical functionality in the revised `02` is covered by at least one Core question.
- `07_exam_procedures.md` main section contains Procedures 0, A, B, D, E, F, H, I, J, K. Procedures **C (Poisson splitting)** and **G (MGF)** have been moved to a collapsed historical appendix.

### Residual coverage notes, stated plainly

- **F29 (conditional variance / EVE law)** is examinable and taught but has **no exam precedent**, so it is covered only by a constructed exercise. This is the one place you must practise on something Louidor has never set.
- **F30 (Wald / random sums)** is examinable but its best specimen now sits inside an excluded question, so it is covered only by the isolated 2024wA Q4(a) drill plus 2017spB Q7.
- **F24 (non-monotone transformations)** is covered only by an Extra item with **no official solution** in the folder — you will have to check your own work.
