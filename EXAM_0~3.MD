# 06 — The smallest representative question set
### Revised against Prof. Louidor's official Spring 2026 announcement

**Officially excluded from the Spring 2026 exam:** moment generating functions · simulation · couplings · Poisson processes · the Poisson–Gamma relationship · the Beta distribution · the Chernoff bound · the multivariate normal distribution · almost-sure convergence · Borel–Cantelli lemmas.

**Officially confirmed format (Moed A and Moed B):** 4 open questions × 5 subparts, subparts increasing in difficulty, 5 points each, 100 points total. The 16-question multiple-choice format applies only to the special moed and is not your target.

**Selection rule after the announcement.** A question enters the Core set only if its *main required techniques* are examinable. Where a question is mixed, the excluded subparts are named and you are told to skip them. No question is selected on the strength of a single isolated subpart.

**Totals:** Core = 10 questions (49 subparts to solve, 1 to skip). Variation = 8. Extra = 6. Redundant and Excluded listed at the end.

---

# CORE SET

---

### C1 — 2024wA Q1 (a–e) · binary vectors as matrix rows
**Source:** `df62117f` Q1 · **Spring 2026 status: Examinable** · **Excluded elements: none**
**Solve: (a) (b) (c) (d) (e).** Skip: nothing.

**Skills:** F02, F03, F12, F10, F14, F15.
**Why selected:** The densest Family A specimen in the folder, from the most recent Moed A. (a)–(c) show three accepted routes each; (e) has the hardest overlap classification anywhere in the bank.
**What makes it different:** Three overlap classes in (e) — `i=r,j=t` / `i≠r,j=t` / `i≠r,j≠t` — because the rows are drawn without repetition.
**Makes redundant:** 2023spB Q1d,e · 2020spB-sol Q5 · 8598-sol Q12 · 2018wA Q13.
**How to work it:** (a)–(d) unaided. (e) attempt 15 min, then study the pair-counting.
**First hint:** In (c), before computing, ask what happens when `k` exceeds the number of binary vectors starting with a zero.
**Time:** Long.

---

### C2 — 2024wA Q2 (a–e) · moments of the standard normal
**Source:** `df62117f` Q2 · **Spring 2026 status: Examinable** · **Excluded elements: none.** *Checked specifically: this question computes moments by direct integration and integration by parts. It does not use an MGF at any point, so the MGF exclusion does not touch it.*
**Solve: (a) (b) (c) (d) (e).** Skip: nothing.

**Skills:** F41, F40, F34, F42.
**Why selected:** The only question that runs analysis technique (parity, integration by parts, boundary terms) into probability technique (Markov). (e) is the cleanest documented "you must reuse (d)" case.
**What makes it different:** Markov applied to `|X − E(X)|^n`, not to `X`.
**Makes redundant:** 2021spB Q6d at the technique level.
**How to work it:** (a)–(c) unaided. Hint on (d). (e) unaided after (d).
**First hint:** In (a) you do not need to integrate. Look at the parity of the integrand and check convergence.
**Time:** Medium.

---

### C3 — 2024wB Q1 (a–e) · maximum and minimum of n dice
**Source:** `83f1db1c` Q1 · **Spring 2026 status: Examinable** · **Excluded elements: none.** *Order statistics is not a named syllabus topic but is reachable entirely from "distribution of a function of a random variable" plus independence, both examinable. Nothing here touches the exclusion list.*
**Solve: (a) (b) (c) (d) (e).** Skip: nothing.

**Skills:** F33, F17, F23, joint CDF → joint PMF.
**Why selected:** The complete Family F development in five graded steps, ending in the four-corner conversion — the most error-prone algebraic step in the bank.
**What makes it different:** It is discrete, so off-by-one handling and step functions `u(x−y)` matter.
**Makes redundant:** 2018wA Q4,Q5 · 2018wB Q13 · 2022spC Q8,Q9 · 2020spB-sol Q3.
**How to work it:** (a)–(d) unaided. (e) attempt, then check sign by sign.
**First hint:** For (c), write `P(X≤x, Y≤y) = P(X≤x) − P(X≤x, Y>y)`; the second term forces every die into the band `(y, x]`.
**Time:** Long.

---

### C4 — 2024wB Q2 (a–e) · sum, difference and mod-1 of uniforms
**Source:** `83f1db1c` Q2 · **Spring 2026 status: Examinable** · **Excluded elements: none**
**Solve: (a) (b) (c) (d) (e).** Skip: nothing.
**Note:** the official solution for this question is a handwritten scan.

**Skills:** F17, F25, F24, plus a concept jump to an arbitrary density.
**Why selected:** The clearest concrete→general ladder. (e) asks for the density of `(W + V) mod 1` for a general `f_W`; the answer is `U(0,1)` — a structural fact.
**Makes redundant:** 2018wA Q10 · 2017spB Q14.
**How to work it:** (a)–(c) unaided. (d) attempt 15 min then read. (e) unaided after (d).
**First hint:** For (d), split on whether `U+V < 1` or `≥ 1`; `Z = z` is reachable in exactly two ways.
**Time:** Long.

---

### C5 — 2024wB Q3 (a–e) · balls repainted white
**Source:** `83f1db1c` Q3 · **Spring 2026 status: Examinable** · **Excluded elements: none**
**Solve: (a) (b) (c) (d) (e).** Skip: nothing.

**Skills:** F09, F11, F14, F10.
**Why selected:** (d) contains the most instructive single idea in the folder — tag a specific ball and ask whether it was ever drawn, giving `1 − ((n−1)/n)^{k−1}` in one line. (e) is coupon-collector by decomposition.
**What makes it different:** Draws are *with* replacement but the state still changes.
**Makes redundant:** 2020spA-sol Q13,Q14.
**How to work it:** (a)–(c) unaided. (d) attempt 10 min; if the tagging idea does not come, read it. (e) unaided.
**First hint:** For (d), forget the process. Number the balls. What is the chance *this particular ball* was never selected in the first `k−1` draws?
**Time:** Medium.

---

### C6 — 2023spB Q4 (a–e) · machine that makes bolts *(REPLACEMENT for the removed 2024wB Q4)*
**Source:** `a1e1cda2` Q4 · **Spring 2026 status: Examinable** · **Excluded elements: none.**
*Explicitly checked: this is a hierarchical **univariate** normal model. The joint law of `Y_1,…,Y_n` given `X` is handed to you as an explicit product of independent univariate normals, and Louidor's own solution does the marginal by **completing the square**, not by invoking a normal vector or a covariance matrix. The multivariate-normal exclusion does not bite. No MGF, no Poisson, no Gamma appears anywhere in the question.*
**Solve: (a) (b) (c) (d) (e).** Skip: nothing.

**Setup:** `X ~ N(0,1)` is the length the machine is calibrated to; given `X = x`, the bolts `Y_1, Y_2, …` are iid `N(x, 1)`.
(a) `E[Y_1]` · (b) the density `f_{Y_1}(y)` · (c) the conditional density `f_{X|Y_1}(x|y)` · (d) `E(X | Y_1 = y)` · (e) `E(Y_2 | Y_1 = y)`, with proof.

**Skills:** F28 tower law · F06 continuous total probability · F20 marginal by integrating out · **F47 completing the square in a normal integral** · F08/F21 continuous Bayes producing a full posterior density · **F48 conditional independence given a latent variable**.

**Why selected:** Removing 2024wB Q4 left the Core set without a question that (i) obtains a marginal density by integrating a conditional against a prior, and (ii) produces a full posterior density and then smooths over it. This question does both, in the officially confirmed 5-subpart shape, from a Moed B paper, with a complete typed official solution. It is the strongest examinable question in the folder that no other Core item covers.

**What makes it different:** The answers are interpretable, which makes them self-checking. `Y_1 ~ N(0,2)` — variance 1 from the calibration plus 1 from the machine. `X | Y_1 = y ~ N(y/2, 1/2)` — the posterior mean shrinks the observation halfway toward the prior mean. `E(Y_2|Y_1=y) = y/2` — you predict the *next* bolt using the posterior on the machine, not the observation itself. Nothing else in the bank rewards a sanity check this directly.

**Makes redundant:** 2018wA Q2 · 2019spB Q11 · 8598-sol Q5 · 2020spA-sol Q3 (conditional with an x-dependent support is still carried by V4).

**How to work it:** (a) unaided. (b) attempt 20 minutes — the completion of the square is the whole point; if it stalls, read it and then reproduce it from memory the next day. (c) unaided using (b). (d) unaided. (e) attempt unaided; the trap is answering `0`.

**First hint:** In (b), write the product of the two exponentials and collect the exponent as a quadratic **in `x`**. Complete the square in `x`. Whatever is left over that depends only on `y` is your answer, up to a constant.

**Time:** Medium.

---

### C7 — 2023spA Q2 (a–e) · boys not chosen at the dance
**Source:** `769b5b18` Q2 · **Spring 2026 status: Examinable** · **Excluded elements: none.** *Subpart (e) proves convergence **in probability** via Chebyshev. Almost-sure convergence and the strong law are excluded, but neither is used or needed here.*
**Solve: (a) (b) (c) (d) (e).** Skip: nothing.

**Skills:** F14, F15, F35, F36, limits of `(1 − x/n)^n`.
**Why selected:** The canonical Family H template. (e) is the exact proof structure Louidor expects, written out in the official solution.
**What makes it different:** `E(X_n) ≠ L`, so plain Chebyshev is unavailable.
**Makes redundant:** 2021spA Q6d · 2021spA Q7c.
**How to work it:** (a)–(d) unaided. (e) attempt 20 min, then study the proof and rewrite it from memory the next day.
**First hint:** You cannot apply Chebyshev to `|X_n − L|` directly. Insert `E(X_n)` and split.
**Time:** Long.

---

### C8 — 2023spA Q3 (a–e) · U ~ Unif[1,2], T | U=u ~ Exp(u)
**Source:** `769b5b18` Q3 · **Spring 2026 status: Examinable** · **Excluded elements: none.** *Exponential conditional laws are not a Poisson process — there is no counting process, no arrival times and no Poisson-distributed count anywhere in the question.*
**Solve: (a) (b) (c) (d) (e).** Skip: nothing.

**Skills:** F21, F28, F06, F17, F08.
**Why selected:** The complete Family B template, and the only clean specimen of conditioning on an **event** `{T>t}` rather than on a value.
**What makes it different:** (b) needs `E(1/U) = ln 2`. (e) needs the CDF from (c) as its denominator.
**Makes redundant:** 2019spB Q5 · 2022spC Q4 · 2021spB Q2.
**How to work it:** All five unaided if you have done T11.
**First hint:** In (e) the conditioning event is `{T > t}`, not `{T = t}`. Bayes with `P(T>t|U=u)` on top and `1 − F_T(t)` underneath.
**Time:** Medium.

---

### C9 — 2023spA Q4 · weighted tree with N(0,1) edges — **MIXED QUESTION**
**Source:** `769b5b18` Q4 · **Spring 2026 status: Mixed question**
**Excluded element: subpart (d)** — "find the **joint distribution** of `X_i` and `X_j`". The official answer is a bivariate normal written with a 2×2 covariance matrix. **Multivariate normal is officially excluded.**
**Solve: (a) (b) (c) (e). SKIP (d).**

**Skills retained:** F26 sums of independent normals (univariate) · F27 covariance by counting shared components · converting graph distance into a shared-edge count.
**Why still selected:** (c) is the best specimen of covariance-by-shared-components in the bank, and (e) is a clean edge-multiplicity counting exercise ending in a univariate normal. Four of the five subparts survive intact, so this passes the "not a single isolated subpart" test comfortably.
**What makes it different:** `Cov(X_i, X_j) = 3 − d/2` — you must convert "distance `d` between two leaves" into "number of shared root-path edges."
**Makes redundant:** nothing now — 8598-sol Q16 and c2adcfa6 Q7 were its former dependants and are themselves excluded (both are multivariate normal).
**How to work it:** (a)–(c) unaided. **Do not attempt (d).** (e) unaided.
**First hint:** In (c), write both leaf weights as explicit sums of `W`'s. Covariance is bilinear and `Cov(W_a,W_b) = 0` unless `a = b`, so the answer counts something.
**Time:** Medium (shorter than before, since (d) is dropped).

---

### C10 — 2023spB Q2 (a–e) · estimating an exponential rate by 1/X̄
**Source:** `a1e1cda2` Q2 · **Spring 2026 status: Examinable** · **Excluded elements: none.**
*Checked carefully, because this question is Gamma-heavy. The Gamma **distribution** remains examinable — only the **Poisson–Gamma relationship** is excluded, and this question never mentions Poisson. The step `X̄ ~ Gamma(n, nλ)` comes from the exponential-to-Gamma convolution (Raviv §16.1, examinable), and in any case the exam **supplies the Gamma density in the hint**. The Beta distribution does not appear.*
**Solve: (a) (b) (c) (d) (e).** Skip: nothing.

**Skills:** F27, Gamma density recognition and the reshape-the-integrand trick, F35, F36.
**Why selected:** The only place you must compute `E[1/X̄]` and `E[1/X̄²]` by reshaping the integrand into another Gamma density and using that it integrates to 1. Also contains the deliberate "the Chebyshev bound exceeds 1 and is useless" remark.
**What makes it different:** (e) offers two accepted routes, showing the boundary of what may be quoted.
**Makes redundant:** 2021spB Q6a,b,c (retained in Extra for CLT numerics) · 2018wB Q9.
**How to work it:** (a) unaided. (b) attempt 15 min then read if needed. (c) unaided with (b)'s method. (d), (e) unaided.
**First hint:** In (b), write out `∫ (1/x)·f_{Gamma(n,nλ)}(x) dx`. The `1/x` lowers the power of `x` by one. What Gamma density is now *almost* inside the integral, and what constant completes it?
**Time:** Long.

---

# VARIATION SET

| # | Question | Spring 2026 status | Solve | Skip | New element | Time |
|---|---|---|---|---|---|---|
| **V1** | 2023spA Q1 (`769b5b18`) coin-elimination game | Examinable | a b c d e | — | Family I: the self-referential equation `P(A) = ⅛P(A) + ⅜ + ⅜·⅔ ⟹ 5/7`, plus reuse of (d) inside (e) | Medium |
| **V2** | 2023spB Q1 (`a1e1cda2`) n rooks on an n×n board | Examinable | a b c d e | — | The same Family A skeleton computed both with and without regard for order, with the official conversion between the two conventions | Medium |
| **V3** | 2023spB Q3 (`a1e1cda2`) bridge deal | Examinable | a b c d e | — | *Nested* conditioning: given North+South hold 8 hearts, the rest re-models as a fresh hypergeometric on 26 cards | Medium |
| **V4** | **NEW** — Family D drill: 2020spA-sol Q12 (`434b3aac`) `P(2X<Y)` for `f = ce^{−(ax+by)}` **+** c2adcfa6 Q1 uniform on a triangle, `E(Y²|X=1)` **+** 2018wA Q3 `Cov(4X,Y)` on a triangle | Examinable | all three | — | **Fills the gap left by removing 2024wB Q4.** Drawing a 2-D support, splitting double-integral limits on a sloped region, and reading a conditional off an x-dependent interval. No open-format question in the bank covers this, so a composite is the only honest option | Medium total |
| **V5** | 2021spA Q5 (`6939831e`/`bf8f753a`) coupon collector | Examinable | a b c | — | *Proving* `X₂ ⫫ X₃−X₂`, then using it to get `Cov(X₂,X₃) = Var(X₂)` in one line | Medium |
| **V6** | 2021spA Q7 (`6939831e`/`bf8f753a`) triangles in G(n,½) | Examinable | a b c | — | Overlap classified by shared vertices in a graph, plus a concentration conclusion | Long |
| **V7** | 2020spB-sol Q2 and Q2′ (`390bc55f`) joint density on `0<x<y<∞` | Examinable | study both routes | — | The **pattern-match** move: recognising `Gamma(2,2) × Uniform(0,x)` "immediately, from uniqueness of the density". Gamma is examinable; no Poisson appears | Short |
| **V8** | 2021spB Q5 (`263e684c`) pooled COVID testing | Examinable | a b c | — | A two-valued RV defined by a decision procedure, a protocol comparison, and an index-shift manipulation to a closed form | Medium |

**Hints for the new item V4.** *(a)* For `P(2X<Y)`: sketch the first quadrant and the line `y = 2x`; fix `x`, and let `y` run from `2x` upward. *(b)* For the triangle: find the equations of the two sloped sides, then note that `Y | X=1` is uniform on the segment cut out at `x=1`, so `E(Y²) = Var + mean²`. *(c)* For `Cov(4X,Y)`: bilinearity pulls the 4 out; you only need `E(XY)`, `E(X)`, `E(Y)` on the triangle.

---

# EXTRA SET

| # | Question | Spring 2026 status | Solve | Skip | Why | Time |
|---|---|---|---|---|---|---|
| **E1** | 2024wA Q3 (`df62117f`) collision-avoidance protocol | Examinable — *checked: independent exponential backoffs, not a Poisson process; no counting process or Poisson-distributed count appears* | a b c d e | — | The only open question on competing exponentials with general `n`; uses `E(max) = E(T₁)+E(T₂)−E(min)` and `min` of two `Exp(1)` is `Exp(2)`. **Official solution is a handwritten scan** | Long |
| **E2** | 2021spB Q6 (`263e684c`) CLT and Markov on variance estimators | Examinable | a b c d | — | Numeric CLT with Φ-table lookups plus a Markov *lower* bound | Medium |
| **E3** | 2021spA Q6 (`6939831e`/`bf8f753a`) repeated stick breaking | Examinable | a b c d | — | Iterated smoothing recursion `E(X_n) = 0.25^{n−1}E(X₁)`; convergence in probability | Medium |
| **E4** | 2018wA Q7 (`46f949ce`) non-monotone transformation | Examinable | — | — | **Promoted — now mandatory.** `Y = X³` for `X≥0`, `X²` for `X<0`. The only clean non-monotone transformation in the bank, and no Spring-2026 tutorial drills it. *No official solution in the folder* | Short |
| **E5** | 2019spA Q11 (`14f2ebe0`) `P(U_(1) > 0.15 | U_(2) = 0.5)`, and 2019spA Q9 order statistic + CLT | Examinable | both | — | Two short high-yield fusions of Family F with conditioning and with the CLT. *No official solutions in the folder* | Short each |
| **E6** | **NEW** — 2021spB Q1 (`263e684c`) toy thrown in a square room | Examinable | — | — | **Replaces the geometric-probability coverage lost when 2024wB Q4 was removed.** The success probability is an *area ratio* `(9 − π·1.5²)/9`, then `Geo(p)` and memorylessness give `E(X|X≥5) = 4 + E(X)`. Full official solution | Short |

**Targeted drill, not a question to sit:** **2024wA Q4(a) only** (`df62117f`). `E(X_1+…+X_N)` with `N ~ Pois(λ)` and `X_i ~ U(0,1)`. This is a clean Wald / random-sum exercise (syllabus item 18, examinable) and is genuinely isolable from its setting. **Do subpart (a) and stop.** Subparts (b)–(e) build a Poisson process over sub-intervals and are excluded. Budget 5 minutes.

---

# REMOVED BECAUSE OF THE OFFICIAL EXCLUSIONS

| Question | Was | Excluded topic | Disposition |
|---|---|---|---|
| **2024wB Q4 (a–e)** — Poisson points in the unit disc | **Core C6** | Poisson processes | **Removed in full.** Its expectation-by-conditioning content is carried by C6-new and C8; its area-ratio content by E6; its order-statistic content by C3 |
| **2021spA Q4** — MGF as a mixture of two Poissons | Extra E4 | MGFs | **Removed in full** |
| **2023spA Q4(d)** — joint distribution of two leaf weights | part of Core C9 | Multivariate normal | **Subpart removed**; (a),(b),(c),(e) retained |
| 2024wA Q4(b)–(e) — nested-interval Poisson splitting | mentioned throughout | Poisson processes | Removed; only (a) survives as a 5-minute drill |
| 2021spB Q4 — ρ between face counts via splitting | Redundant list | Poisson processes | Removed. Route ב' (condition on `N`, multinomial) is examinable but adds nothing over V5/C1 |
| 2017spB Q5 (cars at a junction) · 2019spA Q3 (arrivals) · 2019spB Q13 (customers) · c2adcfa6 Q4 (families arriving) | Redundant list | Poisson processes | Removed |
| 2019spA Q10 · 2019spB Q5 · 2020spB-sol Q1′ · 2020spA-sol Q10 · 8598-sol Q9 · 2017spB MGF item | Redundant list | MGFs | Removed |
| c2adcfa6 Q7 · 8598-sol Q16 · 2017spB Q13 | Redundant list | Multivariate normal | Removed |
| 2018wA Q14, Q15 — `Y ~ Gamma`, `X|Y=y ~ Pois(y)` | Redundant list | Poisson–Gamma relationship | Removed |
| 6637-sol ת'Q5 — uniform prior then repeated Bernoulli | Redundant list | Beta distribution | Removed |
| Whole of 2022spC (`f80d3d50`) and its answer key | Redundant list | Wrong format (multiple-choice = special moed only) | Retained only as a construction bank |

---

# REDUNDANT SET (examinable, but superseded)

| Question(s) | Superseded by | Reason |
|---|---|---|
| 2023spB Q1d,e; 2020spB-sol Q5; 8598-sol Q12; 2018wA Q13 | C1 | Same indicator-then-covariance skeleton, fewer overlap classes |
| 2018wA Q4,Q5; 2018wB Q13; 2022spC Q8,Q9; 2020spB-sol Q3 | C3 | Order statistics via CDF, simpler or continuous-only |
| 2018wA Q10; 2017spB Q14 | C4 | Convolution of two independents |
| 2020spA-sol Q13,Q14 | C5 | Changing-urn chain rule |
| 2018wA Q2; 2019spB Q11; 8598-sol Q5; 2020spA-sol Q3 | C6, V4 | Marginal or conditional from a two-stage continuous model |
| 2021spA Q6d; 2021spA Q7c | C7 | Convergence in probability, same template |
| 2022spC Q4; 2021spB Q2 | C8 | Two-stage conditioning, fewer subparts |
| 2018wB Q9 | C10 | Gamma moments without the reshape trick |
| 2019spB Q3 | V1 | Recursive probability, one state |
| 2019spA Q13 | V3 | Sequential draws without replacement |
| 2022spC Q6,Q7; 2018wB Q3,Q12 | V4, V7 | Marginal from a joint density on a sloped region |
| 2019spA Q1; 2017spB Q1 | C1(a–c), V2 | Standalone counting; the open format never asks this alone |
| 2018wB Q7,Q8 | E3 | Stick breaking in multiple-choice form |
| 2018wB Q6; 2020spA-sol Q6 | C8, V3 | Textbook Bayes with a false-positive rate |
| 2018wA Q9; 2018wB Q2; 2019spB Q4; 2021spA Q3 | E2 | Plain CLT numerics |
| 2017spB Q2; 8598-sol Q8 | — | Pattern-waiting (Family L); no successor in the open era |
| 2018wB Q15,Q16 | E6 | Geometric probability, multiple-choice form |
| 6637-sol ת'Q1–ת'Q4, מ'Q3 | C1, C5, C6, C9 | Orphan solutions; the coins-in-a-circle adjacency variation is covered technique-wise by C1 |

---

## Coverage check against the revised functionality map

Every **Critical** functionality in the revised `02_functionality_map.csv` is covered by at least one Core question:

F01 all · F02 C1,V2 · F03 C1,V1 · F05 C6,C8 · **F06 C6,C8** · **F08 C6,C8** · F11 C5,V1 · F14 C1,C7 · F15 C1,C7 · F17 C3,C4 · **F18 V4** · **F19 V4** · **F20 C6,V7** · F21 C6,C8 · F23 C3,V5 · F25 C4 · F27 C9,C7 · F28 C6,C8 · F33 C3 · F35 C7,C10 · F36 C7,C10 · F42 C2,C7 · F45 all · **F47 C6** · **F48 C6**.

**High**-priority items not reached by the Core set, and their mandatory carriers:
- **F24** non-monotone transformation → **E4 (promoted to mandatory)**
- **F29** conditional variance / EVE law → **no exam precedent exists.** Use the constructed diagnostic in `08_diagnostic.csv` (compute `Var(Y_1)` in C6 two ways). This is the one place where you must practise on something Louidor has never set.
- **F30** Wald / random sums → the isolated **2024wA Q4(a)** drill.
- **F26** univariate sums of normals → C9(a),(b),(e).

**F31 (Poisson splitting) and F32 (MGF) are excluded and are no longer covered by anything — correctly so.**
