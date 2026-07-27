# 04 — Louidor-specific patterns
### Revised against Prof. Louidor's official Spring 2026 announcement

**Officially excluded:** moment generating functions · simulation · couplings · Poisson processes · the Poisson–Gamma relationship · the Beta distribution · the Chernoff bound · the multivariate normal distribution · almost-sure convergence · Borel–Cantelli lemmas.

**Two categories are used throughout this file:**

- 🟢 **LIVE** — a stable Louidor construction that is **currently examinable**. These should drive your study plan.
- 🔴 **ARCHIVED** — a stable Louidor construction built on **officially excluded material**. Historically interesting, evidentially sound, and **irrelevant to your preparation**. Retained so that historical questions are correctly labelled and so that you do not rediscover them and mistake them for signal.

**Evidence grading**

- **Strong** — appears in ≥3 distinct exams, including at least one of the two most recent, with exact citations.
- **Moderate** — appears in 2 exams, or in 3+ but only in the multiple-choice era.
- **Weak** — a single occurrence, or an inference from how a solution is written.

**No claim below is a prediction that a topic will appear.** These are observed regularities in *how* he writes.

---

## 1. Format — now officially confirmed, not inferred

| Year | Moed | Format |
|---|---|---|
| 2017 spring B · 2018 winter A,B · 2019 spring A,B | — | 16 multiple-choice, answer-in-an-interval |
| 2020 spring A,B,C | — | multiple-choice, **parameterised per student** |
| 2021 spring A,B | — | **Hybrid**: 4 multiple-choice + 3 open questions |
| 2022 spring C (Nov 2022, Arieli + Louidor) | C | 16 multiple-choice |
| 2023 spring A,B · 2024 winter A,B | — | **4 open questions × 5 subparts, 5 points each** |

🟢 **Status: OFFICIALLY CONFIRMED.** Louidor's announcement states that Moed A and Moed B use 4 open questions, 5 subparts each, subparts increasing in difficulty, 5 points per subpart, 100 points total. The 16-question multiple-choice format is used **only for the special moed**.

**What changed in this revision:** the previous version of this file inferred the format from the 2023–2024 papers. That inference was correct, but it is now a fact rather than a pattern. **Practical consequence:** the multiple-choice papers (2017–2019, 2020, 2022spC) are demoted from "useful format practice" to "a bank of constructions only" — and, as §2 shows, many of those constructions are now excluded anyway.

---

## 2. Repeated mathematical skeletons

### 🟢 2.1 "Count objects, E by indicators, Var by covariance" — **Strong · LIVE · now the highest-value pattern in the folder**

| Exam | Story | Overlap structure |
|---|---|---|
| 2021spA Q7a,b,c | Triangles in `G(n,½)` | share an edge / share a vertex / disjoint |
| 2023spA Q2b,c | Boys chosen by no girl | equal / distinct |
| 2023spB Q1d,e | Unthreatened rooks | equal / distinct |
| 2024wA Q1d,e | Zeros in a `k×n` binary matrix, rows drawn without repetition | `i=r,j=t` / `i≠r,j=t` / `i≠r,j≠t` |
| 6637-sol ת'Q3 | Coins in a circle, "successful" if it and its clockwise neighbour show heads | adjacent / non-adjacent |
| 2020spB-sol Q5 | Unthreatened squares on an `a×b` board | (expectation only) |
| 8598-sol Q12 | Isolated vertices in a random graph | (expectation only) |

Note the escalation: the expectation-only version belongs to the multiple-choice era; the variance version arrives once the format goes open. **Master 2024wA Q1e and you have covered all of them.**

**Revision note:** this pattern's *relative* weight rises after the announcement, because two of its competitors for exam real estate — Poisson splitting and MGF identification — have been removed entirely. Nothing in this pattern touches the exclusion list.

### 🟡 2.2 "Weights on a tree, sum along the root path" — **Strong · MIXED**

- 2019spB Q15: depth-5 binary tree, **Exp(1)** edge weights.
- 2023spA Q4a–e: depth-3 tree, **N(0,1)** edge weights, same construction.

Four years apart, identical skeleton, different distribution. This remains the clearest evidence that he recycles constructions.

🟢 **Examinable part:** writing each leaf weight as an explicit linear combination of independent weights; mean and variance by linearity and independence; **covariance by counting shared edges** (`Cov = 3 − d/2`); and the *univariate* distribution of the total over all leaves.
🔴 **Excluded part:** 2023spA Q4**(d)**, "find the **joint** distribution of `X_i` and `X_j`" — the answer is a bivariate normal with a 2×2 covariance matrix. **Multivariate normal is excluded. Skip this subpart.**

### 🟢 2.3 "Break a stick, keep the short piece, repeat" — **Strong · LIVE**

- 2018wB Q7, Q8 (multiple-choice, consecutive).
- 2021spA Q6a–d (open): prove `X₁ ~ U(0,½)`, `Cov(X₁,X₂)`, `E(X_n)`, convergence to 0 **in probability**.

The multiple-choice pair became the open question three years later. The convergence claim is in probability, not almost sure — unaffected by the exclusion.

### 🔴 2.4 "Poisson number of items, then split by region" — **Strong · ARCHIVED**

- 2017spB Q5 (cars at a junction) · 2021spB Q4 (die rolled a Poisson number of times) · 2024wA Q4b,c (nested intervals) · 2024wB Q4a–e (nested discs).

**Question 4 of both 2024 papers was a Poisson-splitting question.** Before the announcement this was the single strongest frequency signal in the whole folder. **It is now worth nothing.** Poisson processes are officially excluded.

🟢 **One carve-out:** 2024wA Q4**(a)** — `E(X_1+…+X_N)` for `N ~ Pois(λ)` independent of the summands — is a **random-sum / Wald** exercise (syllabus item 18) and is genuinely isolable from the process setting. Do subpart (a) as a 5-minute drill and stop. Subparts (b)–(e) are excluded.

**This entry is the most important lesson in the file.** The two most recent papers both put their hardest question in a family that is now out of scope. Recent-exam frequency is not a safe proxy for current examinability.

### 🟢 2.5 "Uniform or normal outer parameter, known inner conditional law" — **Strong · LIVE**

- 2023spA Q3a–e: `U ~ Unif[1,2]`, `T|U ~ Exp(U)`; asks E, CDF, density, and the **posterior** on `U` given the event `{T>t}`.
- **2023spB Q4a–e**: `X ~ N(0,1)` latent, `Y_i | X=x` iid `N(x,1)`; asks E, marginal density, posterior density, posterior mean, and the prediction for the next observation.
- 2021spB Q1: geometric whose success probability is a geometric-area ratio, then memorylessness.

🔴 2019spB Q5 has the same outer/inner shape but asks for an **MGF value** — excluded.

**Revision note:** 2023spB Q4 was under-weighted in the previous version of this analysis. With Poisson splitting removed it becomes the strongest carrier of this pattern and is now Core question C6.

### 🟢 2.6 "Estimate an unknown parameter, then show the estimator converges" — **Moderate · LIVE**

- 2023spB Q2a–e: estimate `λ` by `1/X̄`; `E[L_n]`, `Var[L_n]` via Gamma integrals; Chebyshev; weak convergence.
- 2021spB Q6a–d: estimate `σ²` by `S` and `T`; CLT approximations; Markov.

Two consecutive-year Moed B papers with a statistical-estimation flavour. **Checked against the exclusions:** 2023spB Q2 is Gamma-heavy, but the Gamma *distribution* remains examinable — only the **Poisson–Gamma relationship** is excluded, and Poisson never appears in that question. The exam also supplies the Gamma density in the hint.

### 🟢 2.7 "Max and min of the same sample" — **Strong · LIVE**

- 2024wB Q1a–e: max and min of `n` dice, ending in the **joint PMF**.
- 2022spC Q8, Q9 · 2018wA Q4, Q5.

🔴 2024wB Q4e (nearest of a **Poisson** number of points) is the excluded member.

### 🔴 2.8 "MGF given, identify the distribution" — **Strong · ARCHIVED**

2021spA Q4 · 2019spA Q10 · 2019spB Q5 · 2020spB-sol Q1′ · 2020spA-sol Q10 · 8598-sol Q9 · 2017spB MGF item. **Six exams.** Excluded.

---

## 3. Recurring distributions — re-scored against the exclusions

| Construction | Exams | Spring 2026 |
|---|---|---|
| Uniform (continuous) | every exam | 🟢 **Live** |
| Normal (univariate), CLT | every exam | 🟢 **Live** — but *multivariate* normal is excluded |
| Exponential (min/max, memorylessness, competing) | 11 exams | 🟢 **Live** — an exponential *conditional law* is not a Poisson process |
| Indicators | 9 exams | 🟢 **Live** |
| Geometric | 7 exams | 🟢 **Live** |
| Gamma | 7 exams | 🟢 **Live** — the exponential→Gamma convolution is examinable; only the **Poisson–Gamma** link is excluded |
| Hypergeometric | 3 exams | 🟢 **Live** |
| Poisson **distribution** | 8 exams | 🟡 **Live as a distribution** (syllabus item 7). 🔴 Excluded as a **process**: splitting, thinning, spatial points, arrival times |
| MGF | 6 exams | 🔴 **Excluded** |
| Multivariate / bivariate normal | 4 exams | 🔴 **Excluded** |
| Beta | 1 exam | 🔴 **Excluded** |

**On the Gamma family (Strong, and worth stating precisely).** Gamma shows up as: a marginal hiding inside a joint density (2020spB-sol Q2), `N(0,1)² ~ Gamma(½,½)` (2021spB Q2), the distribution of `X̄` for exponentials (2023spB Q2b), and a sum of exponentials. **None of these is the excluded Poisson–Gamma relationship**, which is specifically the duality `P(N_t ≥ n) = P(Γ_n ≤ t)` and the Poisson-conditional-on-Gamma conjugacy of 2018wA Q14/Q15. Gamma remains fully live; he gives you the density in the question when he needs it.

---

## 4. Topics frequently combined in one question

🟢 **Strong · LIVE.** He almost never writes a single-topic question in the open format. Live pairings:

| Combination | Where |
|---|---|
| Combinatorics → indicators → covariance | 2024wA Q1 · 2023spB Q1 |
| Order statistics → joint CDF → joint PMF | 2024wB Q1 |
| Convolution → transformation → a *general* density | 2024wB Q2 |
| Sequential draws → geometric decomposition → coupon collector | 2024wB Q3 |
| Symmetry integral → integration by parts → recursion → Markov | 2024wA Q2 |
| Total probability → geometric → recursion | 2023spA Q1 |
| Indicators → variance → limit → convergence in probability | 2023spA Q2 |
| Conditional expectation → smoothing → CDF → density → continuous Bayes | 2023spA Q3 |
| Smoothing → marginal by integration → completing the square → posterior density → conditional independence | **2023spB Q4** |
| Gamma integrals → Chebyshev → weak convergence | 2023spB Q2 |
| Hypergeometric → nested conditional probability | 2023spB Q3 |
| Normal sums → covariance | 2023spA Q4 (a),(b),(c),(e) |

🔴 **Archived pairings:** "Wald → Poisson splitting → conditional distribution" (2024wA Q4) and "Poisson splitting → conditional probability → covariance → order statistics" (2024wB Q4).

**Practical implication (unchanged):** practise *questions*, and specifically the transition points between subparts. Topic-isolated practice will not prepare you.

---

## 5. Progression from easier to harder within a question

🟢 **Strong · LIVE · now officially confirmed.** The announcement states that subparts increase in difficulty. 2024wA instruction 5 says the same in Louidor's own words: *"הסעיפים ברמות קושי שונות (לרוב הולכים ונעשים יותר קשים בכל שאלה). מומלץ לא להתעכב יותר מידי סעיף אחד."*

Observed shapes, all live:

- **Concrete → general.** 2024wB Q2: `U+V` → `U−V` → `(U+V) mod 1` → `(W+V) mod 1` for an arbitrary density. The last subpart is the concept check.
- **One observation → the general prediction.** 2023spB Q4: `E[Y₁]` → marginal density → posterior density → posterior mean → prediction for `Y₂`.
- **n=1 → n=2 → n=3 → general n.** 2024wA Q3.
- **Compute → bound → prove.** 2023spA Q2: probability → expectation → variance → limit → convergence proof.
- **Named case → recursion → closed form.** 2024wA Q2: `E(Z³)` → `E(Z⁴)` → recursion → `E|Z|ⁿ` → Markov bound.

---

## 6. Information established in one part and reused later

🟢 **Strong · LIVE · an explicit exam rule.** 2024wA instruction 6: *"ניתן להשתמש בתשובה הסופית של סעיף אחד בפתרון של סעיף שני, גם אם לא פתרתם את הסעיף הראשון."*

Documented live chains:

| Chain | Citation |
|---|---|
| `E\|Z\|ⁿ` from (d) is *required* by the Markov bound in (e) | 2024wA Q2d → Q2e |
| The indicators defined in (d) are explicitly reused: *"נחשב את E(X₀²) בעזרת האינדיקטורים שהוגדרו בסעיף הקודם"* | 2024wA Q1d → Q1e |
| `P(A)` for `n=2` from (d) is substituted into the `n=3` recursion in (e) | 2023spA Q1d → Q1e |
| `Var(X_n)` from (c) drives the Chebyshev step in (e) | 2023spA Q2c → Q2e |
| `F_T(t)` from (c) is the denominator of the Bayes step in (e) | 2023spA Q3c → Q3e |
| **The marginal `f_{Y₁}` from (b) is the denominator of the posterior in (c); the posterior mean from (d) *is* the answer to (e)** | **2023spB Q4b → Q4c → Q4d → Q4e** |
| `E[L_n]`, `Var[L_n]` from (b),(c) feed the Chebyshev bound in (d) | 2023spB Q2b,c → Q2d |
| `P(A_1)` from (b) gives `E(X)` in (d) and combines with `P(A_1∩A_2)` in (e) | 2023spB Q1b → Q1d,e |

2023spB Q4 is the tightest chain in the folder — four of its five subparts feed directly into the next. That is a further reason it replaced 2024wB Q4 in the Core set.

---

## 7. Traps

### 🟢 7.1 Conditioning traps — **Strong · LIVE**
- **Conditioning that changes the sample space.** 2023spB Q3d,e: given North+South hold 8 hearts, the rest re-models as a fresh hypergeometric on 26 cards.
- **Conditioning on a continuous variable.** 2023spA Q3 and 2023spB Q4 both require the integral form of total probability throughout.
- **Conditioning on an event, not a value.** 2023spA Q3e asks for `f_{U | T>t}` — an event of positive probability, a different formula.
- **Conditional independence that is not unconditional independence.** 2023spB Q4e: `Y₁` and `Y₂` are independent *given* `X`, but dependent unconditionally. Answering `E(Y₂|Y₁=y) = 0` is the trap.

### 🟢 7.2 Support traps — **Strong · LIVE**
- 2024wB Q1c: `P(X≤x, Y≤y)` requires splitting on `x ≥ y`; the official answer carries a step function.
- 2024wA Q1c: the answer is **identically zero** when `k > 2^{n−1}`. He opens the official solution with this.
- Family D joint densities on `0<x<y<∞` or `|x|<y` — the support *is* the question.

### 🟢 7.3 Dependence traps — **Strong · LIVE, with one archived member**
- Assuming independence to compute a variance (the whole point of §2.1).
- 🔴 The 2021spB Q4 trap (correlation is 0, justified by Poisson splitting) is **archived** — excluded.
- 🔴 The 2024wB Q4d trap (counts over *overlapping* regions are not independent) is **archived** — excluded.
- 🟢 The live replacement: 2023spB Q4e, where two observations are conditionally but not unconditionally independent.

### 🟢 7.4 Symmetry traps — **Moderate · LIVE**
Used legitimately in 2023spB Q3a, 2024wA Q1d, 6637-sol ת'Q1b. But 2024wA Q1c cannot be done by symmetry once the degeneracy bites.

### 🟢 7.5 Boundary / degenerate-case traps — **Strong · LIVE**
- Stated constraints (`n ≥ 2`, `α ≥ 1`, `n ≥ 3`) exist because a later step needs them. 2023spB Q2 requires `n ≥ 3` because `Var[L_n]` involves `Γ(n−2)`.
- Geometric off-by-one: 2021spB Q1's `E(X | X ≥ 5) = 4 + E(X)`.
- 🔴 The `N=0` convention trap in Poisson "all points satisfy P" questions is **archived** — excluded.

### 🟢 7.6 A bound that is useless — **Strong, deliberate · LIVE**
2023spB Q2d: *"הערה: נשים לב שחסם צבישב לא עוזר לנו כאן מכיוון שמקבלים חסם גדול מאחד."* He asks for the bound anyway, and the remark is part of the expected answer. Do not assume you made an error.

---

## 8. Tutorial techniques disguised by different wording

🟢 **Moderate to Strong · LIVE** (excluded rows removed):

| In the tutorial it is called | In the exam it appears as |
|---|---|
| "the indicator method for expectation" (T6) | "what is the expected number of unthreatened rooks / triangles / zeros" |
| "smoothing formula" / "tower law" (T7, T11) | "a bolt was measured at length y — what is the expected length of the next one" |
| "Chebyshev's inequality" (T12) | "show that `X_n` converges weakly to `L`", with the ε-definition supplied |
| "Bayes' rule" (T2) | "for `t>0`, find the density of `U` given `{T>t}`" · "find the conditional density of the length the machine was calibrated to" |
| "convolution theorem" (T11) | "find the density of `Z = (U+V) mod 1`" |
| "distribution of a function of an RV" (T9, T11) | "find the joint probability function of the maximum and the minimum" |
| "memorylessness" (T3, T9) | "given that the toy has been thrown at least 5 times" |
| "hypergeometric" (T3) | "how many hearts does North hold" |
| "conditional independence" (T11) | "independently of the other bolts the machine produced" |

🔴 Removed from this table: "multinomial → the number of rolls on which each face appeared" (its exam role was inside excluded splitting questions).

---

## 9. Preferred methods when several solutions exist

🟢 **Strong · LIVE.** His official solutions routinely present two or three routes ("דרך א'", "דרך ב'", "דרך ג'") — 2024wA Q1a–d, 2023spB Q1a–e and Q3a–e, 2024wB Q4b,c. This tells you what counts as valid.

Live preferences:

| Situation | His first route | Also accepted |
|---|---|---|
| Counting a sub-population sampled without replacement | direct equally-likely count `\|A\|/\|Ω\|` | hypergeometric with named parameters |
| Expected count of similar objects | linearity with symmetry | indicators written out in full |
| `E` of a random sum | **Wald's formula** | tower law |
| A joint density that factorises into known pieces | **pattern-match: "immediate from uniqueness of the density"** | integrate the marginal explicitly |
| Weak convergence | **Chebyshev + triangle inequality** | continuity + WLLN (2023spB Q2e offers this as route א') |
| Odd moments of a normal | **symmetry, "can be solved immediately"** | split the integral at 0 |
| `E` of a non-negative integer RV | tail formula `Σ P(X>k)` | direct definition |
| A normal-on-normal marginal or posterior | **complete the square, then "the integral of a density is 1"** | (no shorter route offered) |

🔴 Removed: "a Poisson number of items split by category → splitting in one line, or total probability with `Bin(n,p)` inside".

**Practical implication.** Quote named theorems when you can — he does. He also writes out the long derivation as an alternative, so the long route earns full marks.

---

## 10. Expected level of justification

🟢 **Strong · LIVE · stated in every open exam's instructions.**

- 2024wA rule 7: justify every claim and every computation; you may use any theorem from lectures or tutorials.
- 2023spB rule 12: **unsimplified expressions lose points.** Sums and integrals must be evaluated unless the question says otherwise.
- But 2024wB Q3e says *"ניתן להשאיר את התשובה כסכום"* — he tells you when a sum may be left. Read the per-subpart remarks.
- 2024wA rule 10 / 2023spB rule 11: a distribution may be given as a PMF, density, CDF, ~~MGF~~, or name+parameters. **The MGF option is no longer available to you.**

His own register: *"מלינאריות התוחלת"*, *"לפי נוסחת ההחלקה"*, *"משיטות האינדיקטורים"*, *"מאי-תלות"*, *"כאשר השתמשנו בהשלמה לריבוע"*. Copy it.

---

## 11. Patterns that persist across both formats

🟢 **Strong · LIVE.**

1. **The answer must be a specific number or closed form.** Multiple-choice required landing in an interval; the open format penalises unsimplified expressions. Same demand.
2. **Every question is a composite.**
3. **Consecutive questions share a setup** in the multiple-choice era (2018wA Q4/Q5, 2018wB Q7/Q8, 2022spC Q6/Q7) — this is the *ancestor* of the five-subpart structure.
4. **Real-world dressing is always thin.** Cats, cereal toys, bridge hands, rooks, bolts. Strip it in one line.
5. **He reuses his own constructions across years.** ⚠️ But see §2.4: two of his most-reused constructions are now excluded, so the multiple-choice bank is a much weaker preview than it looked.

---

## 12. Things I checked and could NOT establish

| Claim | Status |
|---|---|
| "2021spB Question 5 lacks a provided solution" (earlier session) | **Not confirmed.** `263e684c` contains full official solutions to Q5(a),(b),(c), including the bonus closed form. Discard that note. |
| Which exam `6637e9a6` solves | **Unresolved.** No matching paper in the folder. Content suggests a combined M+T Moed A. Its ת'Q5 relies on a **Beta** posterior and is excluded; ת'Q1–ת'Q4 and מ'Q3 are examinable. |
| Which exam `8598bddd` solves | **Unresolved.** Date field OCR-damaged; header style matches the 2017 papers. Its Q9 (MGF) and Q16 (multivariate normal) are excluded. |
| ~~Whether Poisson splitting may be quoted on the Spring 2026 exam~~ | **RESOLVED by the announcement: Poisson processes are excluded entirely.** The previous "practise the derivation instead" recommendation was wrong and has been withdrawn. |
| Whether 2018wA Q12 (time between women / between men entering a shop) is a Poisson process or merely competing exponentials | **Requires inspection.** It is a multiple-choice item in the Redundant set either way, so it does not affect the plan. |
| Whether 8598-sol Q4 (a Poisson mixture) counts as a process | **Requires inspection.** Redundant-set item; does not affect the plan. |
