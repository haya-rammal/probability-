# 09 — Final study route
### Revised against Prof. Louidor's official Spring 2026 announcement

---

## 0. What you are preparing for

**Officially confirmed (Moed A and Moed B):**
- 4 open questions
- 5 subparts per question, **increasing in difficulty**
- 5 points per subpart, 100 points total
- Closed book. The official **formula sheet** and **distribution tables** are provided. Simple non-graphing calculator allowed.
- Written setup and justification are required. Unsimplified expressions lose points (2023spB rule 12).

*(The 16-question multiple-choice format applies only to the special moed and is not your target. Older multiple-choice papers are a bank of constructions, not a rehearsal.)*

**Officially excluded:** moment generating functions · simulation · couplings · Poisson processes · the Poisson–Gamma relationship · the Beta distribution · the Chernoff bound · the multivariate normal distribution · almost-sure convergence · Borel–Cantelli lemmas.

**Everything else taught in a lecture or tutorial is examinable.** That is the operative rule, and it is why this route is built from the *taught material* rather than from exam frequency.

---

## 1. The single most important thing this revision changed

Before the announcement, the two strongest frequency signals in the whole folder were:

1. **Poisson splitting** — question 4 of *both* 2024 papers.
2. **MGF identification** — six separate exams.

**Both are now out of scope.** If you had studied by "what does he ask most often in recent papers", you would have spent a substantial share of your preparation on material that cannot appear. The weight has been reallocated to families that are examinable *and* taught this semester:

- **Indicators + covariance** (Family A) — already top, now clearly first.
- **Joint continuous densities** (Family D) — previously had no Core representative; now covered by the composite drill V4.
- **Two-stage / latent-variable conditioning** (Family B) — now carries the replacement Core question **2023spB Q4**.
- **Conditional variance / the EVE law** — examinable, taught in T7, and with **no precedent anywhere in the exam bank**, which raises rather than lowers its expected value.

---

## 2. Skills to repair first

Each should take under an hour. If the matching diagnostic in `08_diagnostic.csv` fails, come back here.

| # | Repair item | Source | Why first |
|---|---|---|---|
| 1 | Ordered vs. unordered counting; one convention in numerator and denominator | T0 `49d5c3cf`, T1 `832a69d8` | Every Family A question opens with two or three counting subparts |
| 2 | The distribution tables: support, mean, variance for Bernoulli, Binomial, Geometric, Hypergeometric, Poisson, Uniform, Exponential, Gamma, Normal. **Ignore the MGF column and the Beta row.** | `cbdd9faa` + `8170482b` | These sheets are given in the exam; knowing *where* things are is worth minutes |
| 3 | Writing `X = Σ I_k` fluently, and stating that linearity needs no independence | T6 `a2c4e67c` | Prerequisite for the highest-value family |
| 4 | `Cov(X,Y) = E(XY) − E(X)E(Y)`; bilinearity; `Var(ΣX_i) = ΣVar + Σ_{i≠j}Cov` | T7 `ed2dc23f` | Prerequisite for every variance-of-a-count question |
| 5 | Tower law `E(X) = E(E(X|Y))`, with `E(X|Y)` understood as a random variable | T7, T11 `6d032398` | Prerequisite for Families B and J |
| 6 | **Conditional variance and the EVE law**, `Var(X) = E(Var(X|Y)) + Var(E(X|Y))` | T7 `ed2dc23f`, Raviv §10.5 | Examinable, taught, and untested in the whole bank — see §1 |
| 7 | Sketching a 2-D support and reading integration limits off the sketch | T10 `e8f2b111`, T11 | Prerequisite for all of Family D |
| 8 | The CDF method: `P(g(X) ≤ y)` rewritten as an event about `X` | T8 `82c0ba5e`, T9 `4924c945` | Prerequisite for Families E and F |
| 9 | **Completing the square** in a normal integral | T9, T10; Raviv §12, §14.2 | The load-bearing step of the replacement Core question |
| 10 | `E(X̄) = μ`, `Var(X̄) = σ²/n`; Markov; Chebyshev; the CLT standardisation `σ√n` | T12 `409f3595` | Prerequisite for all of Family H |

**Removed from this list in the revision:** "MGFs — self-study, no tutorial exists". MGFs are excluded; do not study them.

---

## 3. Current tutorials to review, in priority order

| Priority | Tutorial | Why | Carve-outs |
|---|---|---|---|
| 1 | **T6** `a2c4e67c` — expectation, indicators | Highest transfer in the course; six indicator items | none |
| 1 | **T7** `ed2dc23f` — conditional expectation, smoothing, variance, covariance | Feeds Families A, B, K; also the only source for the EVE law | none |
| 1 | **T12** `409f3595` — inequalities, CLT, LLN | Feeds all of Family H; Chebyshev ×11 | Chernoff and the strong law are **excluded** — T12's Markov/Chebyshev focus is now exactly right |
| 2 | **T11** `6d032398` — conditional expectation continuous; 8 transformation items; 3 convolution items | Feeds Families B, D, E | none |
| 2 | **T10** `e8f2b111` — joint distributions | Feeds Family D | Headed **חורף תשפ"ד**, i.e. reused material — confirm scope with the lecturer |
| 3 | **T9** `4924c945` — expectation, variance, known continuous distributions | Feeds Families E, F, and the normal-integral work | Univariate normals only; multivariate is excluded |
| 3 | **T8** `82c0ba5e` — continuous RVs, density, uniform | Feeds Families D, E | none |
| 4 | **T3** `6195075d` — Bernoulli, binomial, geometric, hypergeometric | Feeds Families J and the counting subparts | none |
| 4 | **T2** `c7451484` — conditional probability, Bayes | Feeds Families B, I, J | none |
| 5 | **T5** `22602972` — conditional PMF, independence, multinomial | The independence-proof material transfers | **Demoted.** The multinomial drill's main exam role was as the fallback route inside Poisson-splitting questions, which are excluded |
| 5 | T4, T1, T0 | Foundational; covered by §2 | none |

---

## 4. The practice sequence

**Phase 1 — prerequisites** (§2). Then run the diagnostics for F14, F15, F28, F47, F17, F35. Repair anything that fails before continuing.

**Phase 2 — Core set**, in this order (dependency order, not exam order):

1. **C8** — 2023spA Q3 (two-stage conditioning). Most within reach; builds the tower-law habit.
2. **C6** — 2023spB Q4 (bolts / latent normal). Extends C8 into completing the square, posterior densities and conditional independence.
3. **C1** — 2024wA Q1 (counting → indicators → covariance). The highest-value skeleton.
4. **C7** — 2023spA Q2 (indicators → variance → convergence in probability). Extends C1 into Family H.
5. **C3** — 2024wB Q1 (max and min of dice). Order statistics from scratch.
6. **C5** — 2024wB Q3 (repainted balls). Changing urn plus the tagging trick.
7. **C9** — 2023spA Q4 **(a),(b),(c),(e) — skip (d)**. Covariance by shared components.
8. **C10** — 2023spB Q2 (estimating a rate). Gamma reshaping, Chebyshev, weak convergence.
9. **C2** — 2024wA Q2 (normal moments). Analysis technique into Markov.
10. **C4** — 2024wB Q2 (convolution and mod 1). The hardest transformation ladder.

**Phase 3 — Variation set.** V4 first (it fills the Family D gap), then V1, V7, V5, V2, V3, V6, V8.

**Phase 4 — mandatory gap-fillers.**
- **E4** — 2018wA Q7, non-monotone transformation. No tutorial drills this.
- **E6** — 2021spB Q1, geometric probability as an area ratio plus memorylessness.
- The **2024wA Q4(a) drill only** — 5 minutes, Wald / random sums. Stop after subpart (a).
- The **constructed EVE-law exercise** in `08_diagnostic.csv`: compute `Var(Y_1)` in C6 both directly and via `E(Var(Y_1|X)) + Var(E(Y_1|X))`. Both give 2.

**Phase 5 — full mixed exam, timed.**
- Sit **2023spB** (`a1e1cda2`) as a complete 3-hour paper with solutions covered. **This is the only paper in the folder with no excluded content in any of its four questions** — it is your best full mock.
- Then sit **2024wA** (`df62117f`) **questions 1, 2 and 3 only**, in 2 hours 15 minutes. Question 4 is excluded; do not sit it.
- Mark against the official solutions, and check your *justification density* against Louidor's prose, not just your final numbers.

**Phase 6 — remaining Extra set** if time allows: E1, E2, E3, E5.

---

## 5. Topics that are examinable but thinly represented in the old exams

These now carry the highest uncertainty. **Note the framing change:** in the previous version, MGFs and Poisson splitting were listed here as "coverage gaps". They are not gaps — they are out of scope. This list contains only material that is genuinely examinable.

| Topic | Syllabus / taught | Exam bank | What to do |
|---|---|---|---|
| **Conditional variance / the EVE law** | Syllabus item 16; Raviv §10.5; T7 | **No question in the bank uses it as a main step** | **Highest-uncertainty examinable topic.** Learn it properly and do the constructed exercise. A first appearance is plausible precisely because it is fresh |
| **Sum of a random number of independent RVs (Wald)** | Syllabus item 18; Raviv §17.3; T11 lightly | Its best specimen (2024wA Q4a) now sits inside an otherwise excluded question | Do the isolated Q4(a) drill. Make sure you can derive it via the tower law, not only quote it |
| **Non-monotone transformations** | Raviv §5 | 2018wA Q7, 2018wB Q10 — multiple-choice only | Do E4. No Spring-2026 tutorial drills this |
| **Order statistics** | Not a named topic, but fully derivable from item 12 + independence | Heavily represented | Derive `P(max ≤ x) = F(x)^n` each time rather than quoting a density formula |
| **Multinomial** | Raviv §6.2; T5 heavily (12 mentions) | Its exam role was inside excluded splitting questions | Cheap to keep, but do not over-invest |
| **Mixed RVs (§13.3); continuous-but-not-absolutely-continuous (§13.5)** | Raviv covers them | No exam question | Conceptual understanding only |
| **Weak law of large numbers** | Syllabus item 20; T12 | 2023spB Q2e offers it as an accepted route | Know both routes to weak convergence |

**Do not treat any excluded topic as a gap.** MGFs, Poisson processes, Poisson–Gamma, Beta, Chernoff, multivariate normal, almost-sure convergence, Borel–Cantelli, couplings and simulation are simply not on the exam.

---

## 6. The 12 most important functionalities

Ranked by (frequency in the *examinable* portion of the 2023–2024 open exams) × (weight in the Spring-2026 taught material). IDs are from `02_functionality_map.csv`.

1. **F14 — indicator method for expectation.** Six or more exams; the cheapest big win.
2. **F15 — variance of a sum of *dependent* indicators.** The step that separates a 15 from a 25 on a Family A question.
3. **F28 — conditional expectation and the tower law.** Structural to Families B and J.
4. **F06 + F20 — continuous total probability, and obtaining a marginal by integrating a conditional against a prior.** *Promoted:* with splitting gone, this is the general route to results that used to be quoted.
5. **F08 + F21 — continuous Bayes; a full posterior density with the correct support.** Carried by both C6 and C8.
6. **F17 — find a CDF, then differentiate.** The universal transformation tool.
7. **F33 — maxima, minima and order statistics via the CDF.** A whole question in 2024wB.
8. **F27 — covariance and correlation, especially by shared components.**
9. **F18 + F19 — draw the support, then split the integral limits.** *Promoted:* Family D had no Core carrier before this revision.
10. **F35 + F36 — Chebyshev, and convergence *in probability* via the triangle-inequality split.** The exact template appears in both 2023 papers.
11. **F47 + F48 — completing the square in a normal integral; conditional independence given a latent variable.** *New:* isolated while validating the replacement Core question.
12. **F42 + F45 — read all five subparts first and reuse earlier results; name the theorem and simplify the expression.** Pure exam technique, worth several points per paper.

**Just outside:** F25 convolution · F29 conditional variance (thin in the bank, but examinable and untested) · F09/F10 changing urn and legitimate symmetry · F11 Bernoulli-family recognition · F24 non-monotone transformations · F34 Markov on a constructed variable · F37 CLT numerics.

**Removed from the previous ranking:** F32 (MGF identification) and F31 (Poisson splitting) — both excluded.

---

## 7. "Which method should I try?" — decision guide

**Does the question ask for an expected *number* of things?**
→ Indicators. `X = Σ I_k`, `E(X) = Σ P(A_k)`. Do **not** look for the distribution of `X`.
→ If the next subpart asks for the variance: split `E(X²)` into diagonal + off-diagonal and classify the overlap. → Procedure A.

**Is there a two-stage structure — "first draw N/U/X, then …"?**
→ Condition on the outer variable. `E(X) = E(E(X|Y))`.
→ If `N` is a random *count* of summands, independent of them: Wald.
→ If you need a distribution: continuous total probability, then differentiate.
→ **If both the outer law and the inner conditional law are normal:** multiply the kernels, collect the exponent as a quadratic in the *latent* variable, and complete the square. The leftover prefactor is your marginal; dividing gives your posterior. → Procedure B.

**Are you asked about a *second* observation given the first?**
→ They are independent *given* the latent variable, not unconditionally. `E(Y₂|Y₁=y, X=x) = E(Y₂|X=x)`, then smooth over the **posterior** of `X`. → Procedure B, step 8.

**Is a joint density given, with a constraint like `0<x<y` or `|x|<y`?**
→ **Sketch the region first.** Then: does `f` factor into a known `f_X(x)·f_{Y|X}(y|x)`? If yes, read the answer off. If no, integrate with `x`-dependent limits. → Procedure D.

**Is a new variable defined as a function of old ones?**
→ Sum of independents → convolution, and intersect the supports.
→ Anything else → CDF method. Non-monotone → split the domain. → Procedure E.

**Does "max", "min", "closest", "largest" or `X_(k)` appear?**
→ `P(max ≤ x) = F(x)^n`, `P(min > x) = (1−F(x))^n`. Joint statement → `P(X≤x) − P(X≤x, Y>y)`. Discrete → difference consecutive CDF values; joint PMF via the four-corner formula. → Procedure F.

**Does the question say "bound", "at most", "at least" or "converges"?**
→ Only the mean known, variable non-negative → Markov. If it can be negative, construct `|X−c|^n` first.
→ Variance known → Chebyshev. **Check whether the bound exceeds 1 and say so if it does.**
→ "Show `X_n → L` in probability" → triangle-inequality split, union bound, Chebyshev. *(Convergence in probability only — almost-sure convergence is excluded.)*
→ "Approximately", large `n`, Φ supplied → CLT with `σ√n`. → Procedure H.

**Can the process return to its starting state?**
→ Condition on the first round, write `p = c·p + known`, solve. → Procedure I.

**Are objects drawn one by one from a changing pool?**
→ Chain rule with the composition written per step. For "the k-th draw has property P", try symmetry; if not exchangeable, tag one object and ask about *its* history. For "time until all converted", sum geometrics with changing `p`. → Procedure J.

**Are independent normals summed along overlapping paths?**
→ Write explicit linear combinations. Mean and variance by linearity and independence; `Cov` counts shared components; `ρ = Cov/(σσ)`. A single linear combination is univariate normal. **Stop there — do not write a joint/bivariate normal; that is excluded.** → Procedure K.
→ If the weights are exponential, the sum is **Gamma, not exponential**.

**Does the question mention a Poisson number of points in a region, arrival times, splitting or thinning?**
→ **Out of scope.** Poisson processes are excluded. Do not spend time on it.

**None of the above fits?**
→ Strip the story to one line. Ask: what is the *smallest* object whose randomness drives everything? Define it, and condition on it.

---

## 8. Coverage log — what could not be read reliably

| Item | Problem | What I did | Residual risk |
|---|---|---|---|
| `ae6840b9` (2022spC handwritten key) | No text layer; handwritten | Rendered pages 1–2 and read them visually; confirmed it keys `f80d3d50` via Q1's `Cov(I_A,I_B) = 0.012` | Pages 3–7 not transcribed. **No impact** — 2022spC is multiple-choice, the special-moed format |
| `f80d3d50` pages 4–9 | Broken font encoding | Re-rendered at 200 dpi and OCR'd; recovered the mathematics of Q6–Q13 | Q14–Q16 not recovered. **No impact** |
| `df62117f` Q3 solution | Handwritten scan inside a typed document | Question statement read cleanly; solution structure reconstructed from legible fragments | Q3(d),(e) for general `n` not reliably transcribed. This is why E1 sits in Extra, not Core |
| `83f1db1c` Q2 solution | Handwritten scan | Question statement clean; structure reconstructed | C4's solution is harder to verify against. Budget extra time |
| `6637e9a6` | Hebrew extracted with a space between every letter | De-spaced programmatically | Stems recovered; some numerics unverified. Its ת'Q5 is excluded (Beta) |
| `8598bddd` | Several stems lost their mathematical notation; date field damaged | Classified each question by topic | Cannot date it. Its Q9 (MGF) and Q16 (multivariate normal) are excluded; the rest are Redundant |
| `434b3aac` (2020spA solutions) | Q1, 2, 9, 11, 15 absent; exam paper not in the folder | Recorded the gap; confirms the earlier session's note | Five questions unrecoverable. Low impact |
| `390bc55f`, `c2adcfa6` | Solutions only, parameterised (`a`,`b`,`c`), papers missing | Used for method and structure, not numeric practice | V7 is a *study* item, not a *solve* item, for this reason |
| Original filenames | All 49 PDFs stored under UUIDs; no mapping in `metadata.json` | Identified every file from first-page content and cross-matched solutions to papers | Two solution files could not be matched to a dated exam |
| Prior finding: "2021spB Q5 lacks a solution" | — | **Not confirmed** — full official solutions to Q5(a),(b),(c) are present | Discard that note |
| 2018wA Q12; 8598-sol Q4 | Cannot decide whether these are Poisson *processes* or merely competing exponentials / a Poisson mixture | Marked "requires inspection" in `01_source_index.csv` | Both are Redundant-set multiple-choice items; **no impact on the plan** |

---

## 9. One-paragraph summary

The exam is four open questions of five increasingly difficult subparts, closed book with the formula sheet and distribution tables provided, and written justification is marked. Louidor builds his questions from a small set of stable skeletons — but the official exclusions have removed two of the most frequent ones (Poisson splitting, which carried question 4 of *both* 2024 papers, and MGF identification, which appeared in six exams). What remains, and what you should own: *count things and take a variance over dependent indicators*; *condition on an outer or latent variable and smooth, completing the square when everything is normal*; *sketch a joint support and split the integral limits*; *transform via the CDF*; *take a max or min through the CDF*; *bound with Markov or Chebyshev and prove convergence in probability*. Ten Core questions cover all of it, with one subpart to skip (2023spA Q4d, bivariate normal). The one place you must practise on something Louidor has never set is the **conditional-variance / EVE law**, which is taught in T7, is examinable, and has no precedent in the bank. Start with the prerequisite repairs, work the Core set in the order in §4, sit 2023spB as a full timed paper — it is the only paper in the folder that is entirely in scope — and use `08_diagnostic.csv` to decide where to go back.
