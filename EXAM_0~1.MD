# 03 — Question families (grouped by transferable solution structure)
### Revised against Prof. Louidor's official Spring 2026 announcement

**Officially excluded from the Spring 2026 exam:** moment generating functions · simulation · couplings · Poisson processes · the Poisson–Gamma relationship · the Beta distribution · the Chernoff bound · the multivariate normal distribution · almost-sure convergence · Borel–Cantelli lemmas.

**Officially confirmed format (Moed A / Moed B):** 4 open questions × 5 subparts of increasing difficulty, 5 points each, 100 points.

Families are now sorted into three sections:

- **PART 1 — EXAMINABLE FAMILIES** (A, B, D, E, F, H, I, J, M) — these drive your study plan.
- **PART 2 — MIXED FAMILIES** (K) — partly examinable; the excluded step is named and quarantined.
- **PART 3 — HISTORICALLY RECURRING BUT NOW EXCLUDED** (C, G, L and others) — retained for completeness so that historical exam questions are correctly labelled. **Their historical frequency must not inflate current priority.** Do not study them.

**How to read this file.** Families are grouped by *what you actually do*, not by chapter. Two questions are in the same family if mastering one makes the other mechanical.

**Source convention.** `2024wA Q1d` = Winter-2024 Moed A, question 1, subpart ד. Files are identified by the UUID stub used in `01_source_index.csv`. Solutions marked **[official]** are Louidor's own.

---

# PART 1 — EXAMINABLE FAMILIES

## Family A — "Count things with a property": indicators for E, covariance for Var

This is **the single most repeated skeleton in Louidor's open exams.** It appears in some form in every open-format exam in the folder.

**Recognition clues**
- "What is the expected number of …?" followed immediately by "What is the variance of …?"
- The objects being counted are *similar to each other* but *not independent* (they share rows, share vertices, share a pool).
- The story is combinatorial dressing: rooks on a board, triangles in a random graph, boys not chosen, zeros in a matrix, coins in a circle, unthreatened squares.

**General setup**
Define an indicator `I_k = 1{object k has the property}`, let `X = Σ I_k`.

**Reusable solution procedure**
1. Say in words exactly what `I_k` indicates. Give the index range.
2. `E(X) = Σ E(I_k) = Σ P(A_k)` — by linearity only. Say "linearity does not require independence."
3. `P(A_1)` is computed once; symmetry gives `E(X) = n·P(A_1)`.
4. `Var(X) = E(X²) − E(X)²`, with `E(X²) = Σ_k E(I_k²) + Σ_{k≠j} E(I_k I_j) = Σ_k P(A_k) + Σ_{k≠j} P(A_k ∩ A_j)`.
5. **Classify the pairs (k,j) by how much they overlap.** Count how many ordered pairs are in each class. This is where the marks are.
6. Substitute and simplify.

**Variations Louidor uses**
| Variation | Where | What changes |
|---|---|---|
| Two overlap classes (equal / disjoint) | 2023spA Q2c (boys), 2023spB Q1e (rooks) | Simplest form |
| Three overlap classes (same row / same column / disjoint) | 2024wA Q1e (zeros in a k×n binary matrix) | `i=r,j=t` vs `i≠r,j=t` vs `i≠r,j≠t` — must count each class |
| Overlap by *adjacency* on a cycle | 6637-sol ת'Q3 (coins in a circle, "successful" if it and its clockwise neighbour are heads) | Only neighbours are dependent; Cov is non-zero for exactly 2n ordered pairs |
| Overlap by shared vertex | 2021spA Q7b (triangles in G(n,½)) | Triangles sharing an edge vs sharing one vertex vs disjoint |
| Followed by a concentration claim | 2021spA Q7c, 2023spA Q2e | Var/E² → 0, then Chebyshev |

**Hidden intermediate skills**
- F10 symmetry (so you only compute `P(A_1)` and `P(A_1 ∩ A_2)`).
- Counting ordered vs. unordered pairs correctly (`n(n−1)` not `C(n,2)` when you wrote `Σ_{k≠j}`).
- Recognising `E(I_k I_j) = P(A_k ∩ A_j)` because a product of indicators is the indicator of the intersection.

**Common traps**
- Dropping the covariance terms. The exam *always* chooses a dependent case — if the indicators were independent the question would be trivial.
- Trying to find the distribution of `X` first. In 2021spA Q7 the number of triangles has no tractable distribution; the indicator route is the *only* route.
- Miscounting the multiplicity of an overlap class (2024wA Q1e is exactly this trap).

**Representative questions:** 2024wA Q1d+Q1e (best single specimen — three overlap classes), 2021spA Q7a+b+c (hardest, adds concentration), 2023spB Q1d+e (cleanest combinatorial version).

**Similar-looking but different:** 2023spA Q2b/c *looks* identical but the indicators there are for "boy i is chosen by nobody", and the pairwise probability is `(1 − 2/n)^{αn}` — a *different functional form*, not a different method. By contrast 2024wB Q3e (expected time until all balls are white) looks like a counting question but is actually **Family F** (sum of geometrics).

**Spring 2026 status: EXAMINABLE — IN CORE, and now the single highest-value family.** Syllabus items 13 and 14 name it explicitly; nothing in it touches the exclusion list. T6 has six indicator exercises, T7 five covariance exercises. Its relative importance *rises* after the announcement, because two competing families (Poisson splitting, MGF) have been removed entirely.

---

## Family B — Two-stage experiments: condition, then smooth

**Recognition clues**
- "First draw N …, then draw N things."
- "The rate/parameter is itself random."
- A conditional law is *handed to you*: "the distribution of T given U=u is exponential with rate u."

**General setup**
Identify the outer variable (the one you condition on) and the inner conditional law.

**Reusable solution procedure**
1. Write the conditional law explicitly: `X | Y=y ~ Known(θ(y))`.
2. `E(X|Y=y)` from the table; note it is a *function of y*, so `E(X|Y)` is a random variable.
3. `E(X) = E(E(X|Y))` — tower law.
4. For a distribution rather than a mean: continuous total probability `F_X(t) = ∫ P(X≤t|Y=y) f_Y(y) dy`, then differentiate.
5. For the reverse direction (posterior on the parameter): continuous Bayes, `f_{Y|A}(y) = P(A|Y=y) f_Y(y) / P(A)`.

**Variations Louidor uses**
| Variation | Where | Spring 2026 |
|---|---|---|
| U ~ Uniform, T\|U ~ Exp(U); asks E, CDF, density, and the posterior on U | **2023spA Q3 (a–e) — the canonical specimen** | **Examinable** |
| X ~ N(0,1) latent; Y_i \| X=x iid N(x,1); asks E, marginal density, posterior density, posterior mean, and the prediction for the next observation | **2023spB Q4 (a–e) — the new Core specimen** | **Examinable** |
| X ~ Exp(2), E(Y\|X=x)=3x+1; asks E(XY) | 2022spC Q4 | Examinable (multiple-choice format) |
| N ~ Poisson, then N uniforms; asks E(S) via Wald *and* via smoothing | 2024wA Q4a | **Partially relevant** — subpart (a) only, isolable as a random-sum drill |
| N ~ Poisson, then N points in a disc | 2024wB Q4 | **EXCLUDED** (Poisson process) |
| U ~ Uniform[2,3], X\|U ~ Exp(U); asks for an MGF value | 2019spB Q5 | **EXCLUDED** (MGF) |
| Y ~ Gamma, X\|Y=y ~ Pois(y) | 2018wA Q14, Q15 | **EXCLUDED** (Poisson–Gamma relationship) |
| Subscriber draws Q ~ U(0,1) once, then buys with prob Q forever | 6637-sol ת'Q5 | **EXCLUDED** (Beta distribution) |

**Hidden intermediate skills**
- `E(XY) = E(E(XY|X)) = E(X·E(Y|X))` — pulling the known factor out of the conditional expectation (2022spC Q4).
- Knowing that `E(1/X)` for `X ~ Gamma` is done by *reshaping the integrand into another Gamma density* (2023spB Q2b/c — Louidor's own solution does exactly this and then says "the integral of a density is 1"). The Gamma distribution itself remains examinable; only the Poisson–Gamma relationship is excluded.
- **Completing the square** when both the prior and the conditional law are normal, so that the leftover prefactor *is* the marginal density (2023spB Q4b). — functionality **F47**.
- **Conditional independence given a latent variable**: `E(Y₂ | Y₁=y, X=x) = E(Y₂ | X=x)`, then smoothing over the *posterior* of `X` rather than its prior (2023spB Q4e). — functionality **F48**.

**Common traps**
- Using the discrete total-probability formula when the conditioning variable is continuous.
- Treating `E(X|Y)` as a number.
- Forgetting that in the posterior the *support of U is unchanged* but the density is reweighted.

**Representative questions:** 2023spA Q3 (a–e) is the complete template for the *forward-then-posterior* direction. **2023spB Q4 (a–e)** is the complete template for the *latent-parameter* direction and is the replacement Core question. 2024wA Q4a shows the two-route habit but only subpart (a) is usable.

**Similar-looking but different:** 2021spB Q2 (Z = X², W = det of a 2×2 antisymmetric-ish matrix) *looks* like a conditional-density question and is solved by Bayes, but the real work is recognising `W = X² + Y²` and `Z = X²` and using the `N(0,1)² ~ Gamma(½,½)` fact. That is **Family D**. (2021spB Q2 uses `N(0,1)² ~ Gamma(½,½)`, which is a chi-square relationship, not the excluded Poisson–Gamma one — but it is a multiple-choice item and redundant after C8.)

**Spring 2026 status: EXAMINABLE — IN CORE.** Syllabus items 11, 15, 16. Tutorials T7 and T11 are exactly this.

**Removals within this family:** 2024wB Q4 and 2024wA Q4b–e (Poisson-process settings) and 2018wA Q14/Q15 (Poisson–Gamma conjugacy) are **excluded**. 2019spB Q5 asks for an MGF value and is **excluded**. The family's core template, 2023spA Q3, is untouched, and the new Core question **2023spB Q4** (hierarchical normal: marginal by integration, posterior density, conditional independence) now carries the family alongside it.

---

## Family D — Joint continuous distributions: support, limits, marginals, conditionals

**Recognition clues**
- A joint density is given with a constraint like `0<x<y<∞`, `|x|<y`, `x<y<∞, y>0`.
- "uniform on the triangle with vertices …"
- "find `f_Y`", "find `E(Y²|X=1)`", "find `P(2X<Y)`".

**General setup**
**Draw the region first.** Every official solution in this family begins with, or presupposes, a sketch. c2adcfa6 Q1's official solution literally says *"in solving this question it is recommended to sketch the given triangle."*

**Reusable solution procedure**
1. Sketch the support in the (x,y) plane. Label the bounding lines.
2. Normalisation constant if needed: integrate over the region, set to 1.
3. Marginal of X: fix x, read the y-range off the sketch, integrate. **The limits depend on x.**
4. Conditional: `f_{Y|X}(y|x) = f_{X,Y}(x,y)/f_X(x)` — and the support of Y now depends on x.
5. Probability of a region: intersect the support with the event region; split into cases if the boundary changes.
6. Independence check: factorisation **and** rectangular support.

**Variations Louidor uses**
| Variation | Where |
|---|---|
| Uniform on a triangle, asks `E(Y²|X=1)` | c2adcfa6 Q1 — requires finding the line equations of two sides |
| `f = 4e^{-2x}` on `0<x<y<∞`; asks Var(aX) and Var(bY) | 2020spB-sol Q2 and Q2' — **the official solution pattern-matches the joint into `Gamma(2,2) × Uniform(0,x)`** |
| `f = c e^{-(ax+by)}`; asks `P(2X<Y)` | 2020spA-sol Q12 |
| `f = (1/8) y² e^{-y}` on `|x|<y`; asks the marginal of Y and E(Y) | 2022spC Q6, Q7 |
| Uniform on the triangle (0,0),(1,0),(0,1); asks Cov(4X,Y) | 2018wA Q3 |
| Density given only via `f_X` and `f_{Y|X}`; asks E(X+Y) | 2019spA Q15 |
| `f = 2` on `0≤y≤x≤1`; asks the CDF of `Z=XY³` | 2018wB Q3 |

**Hidden intermediate skills**
- **Pattern-matching a joint density into a known product** (F22). This is Louidor's preferred shortcut and his solutions explicitly flag it as "immediate from uniqueness of the density."
- Reading off `E(Y²|X=x)` when `Y|X=x` is uniform on an x-dependent interval: `E(Y²) = Var + mean²`.
- Splitting an integral when `min(3,b)` / `max(1,b−a)` switch branches (2020spB-sol Q6).

**Common traps**
- Integrating `x` from `0` to `∞` when the constraint `x<y` binds.
- Forgetting the support restriction in the conditional density.
- Concluding independence from a factorising formula while the support is a triangle.

**Representative questions:** 2020spB-sol Q2+Q2' (shows both the pattern-match route and the brute-force route), c2adcfa6 Q1 (the triangle), 2020spA-sol Q12 (region splitting).

**Similar-looking but different:** 2023spA Q3 gives you `f_{T|U}` directly and never asks you to draw a region — that is Family B.

**Spring 2026 status: EXAMINABLE — IN CORE, and PROMOTED.** Syllabus items 10, 11. Tutorials T10 and T11. This family had no Core representative before the revision because the open-format papers do not contain a pure Family-D question; the composite drill **V4** in `06` now fills that slot. Two former members are excluded: c2adcfa6 Q7 (bivariate normal) and 2022spC Q6/Q7 (multiple-choice format only).

---

## Family E — Transformations: CDF method, convolution, and the "mod 1" trick

**Recognition clues**
- "find the density of `Y = g(X)`"
- `Z = X + Y`, `Z = X − Y` for independent X, Y
- Anything with `min`, `max`, `floor`, `mod`, or a piecewise definition

**Reusable solution procedure**
1. **Always start from `P(Y ≤ y)` and rewrite the event in terms of the original variables.** Do not guess.
2. Determine the range of `y` for which the answer changes form; you will get a piecewise `F_Y`.
3. Differentiate on each piece; state the support.
4. Sanity check: `∫f_Y = 1`, `f_Y ≥ 0`, `F_Y` continuous and non-decreasing.
5. For a sum of independents: convolution `f_Z(z) = ∫ f_X(x) f_Y(z−x) dx`, and **intersect the two indicator constraints** to get the true integration limits.

**Variations Louidor uses**
| Variation | Where |
|---|---|
| `U+V`, `U−V`, `(U+V) mod 1`, `(W+V) mod 1` for a *general* density W | **2024wB Q2 (a–e) — the ladder from concrete to abstract** |
| `Z = X − Y` for two independents; asks `f_Z(−1)+f_Z(2)` | 2018wA Q10 |
| `Y = X³` if `X≥0`, `X²` if `X<0` | 2018wA Q7 — non-monotone, must split |
| `Y = 1 − 0.5√(4−X²)` | 2018wB Q10 |
| `Y = min(⌊X⌋, b)` for exponential X | 2020spA-sol Q8 — discrete output from a continuous input; uses the tail formula |
| `Y = −b ln(X_1···X_5)` for iid uniforms | c2adcfa6 Q2 — recognise as a Gamma. **Examinable**: this is the exponential→Gamma convolution, not the excluded Poisson–Gamma relationship |
| `Z = e^X + e^{2Y}` | 2017spB Q14 |

**Hidden intermediate skills**
- The "mod 1" result: the sum of *any* independent RV on [0,1] with a `U(0,1)` is again `U(0,1)` mod 1. Louidor builds to this over Q2c→Q2e in 2024wB. This is a *concept* question dressed as computation.
- Recognising `−ln U ~ Exp(1)` and hence a sum of five of them is `Gamma(5,1)`.

**Common traps**
- Differentiating before establishing the piecewise ranges.
- Convolution without intersecting supports → a "density" that does not integrate to 1.
- Non-monotone `g` treated as monotone.

**Representative questions:** 2024wB Q2 (a–e). Then 2018wA Q7 for non-monotone, 2020spA-sol Q8 for the floor.

**Spring 2026 status: EXAMINABLE — IN CORE.** Syllabus item 12. Raviv §5, §6.3, §8.2, §16.1. The exponential→Gamma convolution used in several members is *not* the excluded Poisson–Gamma relationship and remains examinable. 2-D Jacobians are absent from Raviv's notes — skip. c2adcfa6 Q2 (`−b ln` of a product of uniforms) remains examinable.

---

## Family F — Maxima, minima and order statistics via the CDF

**Recognition clues**
- "the maximum/minimum of n independent …"
- `X_(k)` notation
- "the closest point to the origin"
- Two RVs defined as `X = min(U₁,U₂)`, `Y = max(U₁,U₂)`

**Reusable solution procedure**
1. `P(max ≤ x) = ∏ P(X_i ≤ x) = F(x)^n` (needs independence).
2. `P(min > x) = ∏ P(X_i > x) = (1−F(x))^n`.
3. For a *joint* statement about max and min: `P(X≤x, Y≤y) = P(X≤x) − P(X≤x, Y>y)`, and `P(X≤x, Y>y) = (F(x)−F(y))^n` when `x ≥ y`.
4. Convert a joint CDF into a joint PMF by the four-corner inclusion–exclusion:
   `P(X=x,Y=y) = F(x,y) − F(x−1,y) − F(x,y−1) + F(x−1,y−1)`.
5. For `X_(k)` in general: "exactly k of the n fall below c" → Binomial.

**Variations Louidor uses**
| Variation | Where |
|---|---|
| Max and min of n fair dice; five subparts ending in the joint PMF | **2024wB Q1 (a–e) — the full development** |
| `P(X_(6) < c < X_(7))` for a uniforms → Binomial | 2020spB-sol Q3 |
| `P(U_(1) > 0.15 | U_(2) = 0.5)` | 2019spA Q11 — conditional on an order statistic |
| CLT applied to an order statistic: `P(X_(56) > 0.5)` | 2019spA Q9 — fuses F33 with F37 |
| `min(U₁,U₂)`, `max(U₁,U₂)` with *different* uniform ranges | 2022spC Q8, Q9 |
| Longest/shortest of 5 long-jumpers | 2018wA Q4, Q5 |
| `T = max(X₁,X₂,X₃)` from a given CDF | 2018wB Q13 |
| ~~Nearest of a Poisson number of points~~ | ~~2024wB Q4e~~ — **EXCLUDED** (Poisson process) |
| Min of two exponentials inside a bigger story | 2024wA Q3b (handwritten solution: `max{S₁,S₂} = T₁+T₂ − min{T₁,T₂}`, and `min` of two Exp(1) is `Exp(2)`) |

**Hidden intermediate skills**
- The identity `max(a,b) = a + b − min(a,b)`, used to get `E(max)` cheaply.
- `min` of independent exponentials is exponential with the summed rate.
- Discrete order statistics need care with `<` vs `≤` (2024wB Q1b uses `P(X=x)=P(X≤x)−P(X≤x−1)`).

**Common traps**
- Using the product formula without independence.
- Off-by-one in the discrete case.
- Sign errors in the four-corner conversion (2024wB Q1e — the official solution's final expression has three terms with `u(·)` step functions; this is easy to get wrong).

**Representative questions:** 2024wB Q1 (a–e). Then 2020spB-sol Q3 and 2019spA Q11.

**Spring 2026 status: EXAMINABLE — IN CORE.** Order statistics is not a named syllabus topic, but it is fully derivable from "distribution of a function of a random variable" (item 12) plus independence (item 9), both examinable. Nothing in this family touches the exclusion list. Practise the *derivation* rather than quoting an order-statistic density formula.

**One removal:** 2024wB Q4e (nearest of a Poisson number of points) is **excluded**, because the construction is a spatial Poisson process. The order-statistic technique it uses is fully covered by 2024wB Q1.

---

## Family H — Inequalities and convergence in probability

**Recognition clues**
- "bound from above/below the probability that …"
- "show that `X_n` converges weakly / in probability to `L`", usually with the definition supplied as a reminder.

**Reusable solution procedure (the convergence proof)**
1. Compute `E(X_n)` and `Var(X_n)`.
2. Show `Var(X_n) → 0` and `E(X_n) → L`.
3. Triangle inequality: `|X_n − L| ≤ |X_n − E X_n| + |E X_n − L|`.
4. Hence `{|X_n − L| > ε} ⊆ {|X_n − E X_n| > ε/2} ∪ {|E X_n − L| > ε/2}`.
5. Union bound, then Chebyshev on the first term; the second term is eventually empty.
6. Conclude `lim P(|X_n − L| > ε) = 0`.

**Variations Louidor uses**
| Variation | Where |
|---|---|
| Full triangle-inequality proof, after computing Var in an earlier subpart | **2023spA Q2e — the exact template** |
| Two accepted routes: (i) continuity of `1/x` + WLLN, (ii) Chebyshev + triangle inequality | **2023spB Q2e** |
| Chebyshev bound that turns out to be **greater than 1** — the official solution flags this: *"note that the Chebyshev bound does not help us here"* | **2023spB Q2d — a deliberate trap** |
| Markov applied to `\|X − E X\|^n` to get a `C_n/x^n` bound | **2024wA Q2e** |
| Markov to get a *lower* bound on `P(T ≤ σ²)` | 2021spB Q6d |
| CLT numeric approximation | 2021spB Q6b,c; 2021spA Q3; 2019spB Q4; 2018wA Q9; 2018wB Q2 |
| Concentration of a triangle count | 2021spA Q7c |
| Stick length → 0 in probability | 2021spA Q6d |
| ~~Chernoff bound~~ | — **EXCLUDED**; T12 covers only Markov and Chebyshev, which is now exactly right |
| ~~Almost-sure convergence / strong law~~ | — **EXCLUDED**; every convergence question in the bank is in *probability*, so nothing is lost |

**Hidden intermediate skills**
- Making a variable non-negative before Markov (raise to a power, take absolute value).
- Recognising that when `E(X_n) ≠ L` exactly, plain Chebyshev is *not* enough.
- Knowing `Var(X̄) = σ²/n` and `E(X̄) = μ` cold.

**Common traps**
- Applying Chebyshev directly to `|X_n − L|` when the mean is not exactly `L`.
- Not noticing the bound exceeds 1 and presenting it as a real result.
- Standardising with `σ` rather than `σ√n` in the CLT.

**Representative questions:** 2023spA Q2 (a–e) end-to-end, 2024wA Q2e, 2023spB Q2d.

**Spring 2026 status: EXAMINABLE — IN CORE, with two carve-outs.** Syllabus items 19, 20, 21. T12 is the most drilled tutorial (Chebyshev ×11). **Excluded from this family: the Chernoff bound, and almost-sure convergence / the strong law.** Markov, Chebyshev, the weak law, convergence in probability and the CLT are all examinable and unaffected. Every member question listed above survives.

---

## Family I — Recursive / self-referential probability

**Recognition clues**
- "in any other case, continue to another round — with only the players who got heads"
- The game can return to a state identical to the start.

**Reusable solution procedure**
1. Define `A` = the event of interest and note `P(A)` is the unknown.
2. Condition on the outcome of the **first round** only.
3. Identify which branches (a) end the game, (b) reduce to an *already solved* smaller case, (c) **return to the original problem**.
4. Total probability gives `P(A) = c·P(A) + (known terms)`. Solve.

**Variations Louidor uses**
| Variation | Where |
|---|---|
| Coin-elimination game; `P(A) = ⅛P(A) + ⅜·1 + ⅜·⅔` ⟹ `5/7` | **2023spA Q1e** — and note Q1d supplied the `⅔` used here |
| Clown climbing a 4-rung ladder | 2019spB Q3 |
| Balls repainted white; `P(k-th ball is white)` via a complementary "never drawn" argument | 2024wB Q3d — a *different* recursion-avoiding trick |

**Hidden intermediate skills**
- Spotting that an earlier subpart already solved the reduced case (F42).
- Handling the absorbing "no winner" branch with `P(A|·)=0`.

**Common traps**
- Summing an infinite series instead of solving one linear equation (works, but costs time).
- Forgetting the branch where everyone is eliminated.

**Representative question:** 2023spA Q1 (a–e).

**Spring 2026 status: EXAMINABLE — IN CORE.** Falls under syllabus items 3 and 6. No excluded content.

---

## Family J — Sequential draws with a changing urn

**Recognition clues**
- Balls drawn without replacement; or drawn *with* replacement but repainted/relabelled.
- "given that the first k−1 draws were black…"

**Reusable solution procedure**
1. Multiplication rule: `P(A_1 ∩ … ∩ A_n) = P(A_1)P(A_2|A_1)···`.
2. State the composition of the urn at step k explicitly.
3. For "the k-th draw is white", either (a) symmetry, or (b) a complementary event about a *tagged* ball.
4. For "time until all are white", decompose into a **sum of geometrics with changing p** and use linearity.

**Variations Louidor uses**
| Variation | Where |
|---|---|
| Repaint-on-draw; 5 subparts ending in `E(Y) = Σ n/(n−i)` | **2024wB Q3 (a–e)** |
| Urn R red / B blue without replacement; `P(B_i)`, `P(B_i|B_j)` by symmetry | 6637-sol ת'Q1 |
| Gold/silver coins replaced by silver | 2020spA-sol Q13, Q14 |
| Bridge deal, hypergeometric route | 2023spB Q3 (a–e) |
| 30 balls, 20 red; "the last red ball comes before…" | 2019spA Q13 |

**Hidden intermediate skills**
- The *tagged-ball* trick in 2024wB Q3d: instead of tracking the process, ask "what is the probability this specific numbered ball was never drawn in k−1 steps?" `= ((n−1)/n)^{k−1}`. This is a genuinely non-obvious reframing and it is worth internalising.
- Coupon-collector decomposition (2021spA Q5 and 2024wB Q3e are the same idea).

**Common traps**
- Using a fixed probability when the urn changes.
- Coupon-collector sums with the wrong index range.

**Representative questions:** 2024wB Q3 (a–e), 2021spA Q5 (a–c).

**Spring 2026 status: EXAMINABLE — IN CORE.** Syllabus items 3, 6, 9. No excluded content.

---

## Family M — Pure combinatorial counting

**Recognition clues:** "how many codes…", "how many binary vectors…", equally-likely arrangements.

**Occurrences:** 2017spB Q1 (safe codes), 2019spA Q1 (divisibility), 2018wA Q13 (symmetric binary matrices), 2023spB Q1a–c (rooks), 2024wA Q1a–c (binary vectors as matrix rows).

**Spring 2026 status: EXAMINABLE — IN CORE as a *sub-skill*, not as a standalone question.** In the confirmed open format, counting always appears as subparts (a)–(c) of a question whose real content is Family A. 2024wA Q1 is exactly this.

---

---

# PART 2 — MIXED FAMILIES
*Partly examinable. The excluded step is named and quarantined; do the rest.*

## Family K — Normal vectors and covariance along shared paths

**Recognition clues**
- A tree/graph with iid weights on edges; the "weight of a leaf" is the sum along its root path.
- "find the joint distribution of `X_i` and `X_j`"

**Reusable solution procedure**
1. Write each quantity as an explicit linear combination of the underlying independent weights.
2. Mean and variance from linearity and independence.
3. `Cov(X_i, X_j)` = (number of *shared* edges) × (variance of one weight) — by bilinearity, since distinct weights have zero covariance.
4. Translate the graph distance into a count of shared edges (e.g. depth 3, distance d ⟹ `3 − d/2` shared edges).
5. Any linear transformation of a jointly-normal vector is jointly normal ⟹ write the 2-D normal with the computed covariance matrix.

**Variations**
| Variation | Where |
|---|---|
| Normal weights, depth-3 tree, 8 leaves; asks E, Var, Cov, joint law, and the law of the total | **2023spA Q4 (a–e)** |
| **Exponential** weights on a depth-5 binary tree — same skeleton, different distribution | **2019spB Q15** |
| Two balls on the real line, positions `N(1,¼)`; asks about the distance | 6637-sol מ'Q3 |
| Bivariate normal, `E(Y²|X=b)` | c2adcfa6 Q7 |
| Bivariate normal joint density value | 8598-sol Q16 |

**Common traps**
- Adding standard deviations.
- Forgetting that with exponential weights the sum is **Gamma, not exponential** — this is exactly what makes 2019spB Q15 different from 2023spA Q4.

**Representative question:** 2023spA Q4 (a–e).

**Spring 2026 status: MIXED.**

- **EXAMINABLE:** steps 1–3 and the correlation computation. Writing a quantity as an explicit linear combination of independent weights, adding means and variances, and computing a covariance by counting shared components. Also the *univariate* conclusion that a sum of independent normals is normal.
- **EXCLUDED:** step 5 — "any linear transformation of a jointly-normal vector is jointly normal", and writing a 2×2 covariance matrix. **This is the multivariate normal distribution, officially excluded.**

**Consequences for specific questions:**

| Question | Status |
|---|---|
| 2023spA Q4 (a),(b),(c),(e) | **Examinable — retained as Core C9** |
| 2023spA Q4 (d) — "find the joint distribution of `X_i` and `X_j`" | **EXCLUDED — skip this subpart** |
| 2019spB Q15 (same tree, exponential weights) | Examinable, but multiple-choice format; redundant after C9 |
| c2adcfa6 Q7 (bivariate normal, `E(Y²|X=b)`) | **EXCLUDED** |
| 8598-sol Q16 (multivariate normal joint density) | **EXCLUDED** |
| 2017spB Q13 (bivariate normal density, `E(XY)`) | **EXCLUDED** |
| 6637-sol מ'Q3 (two balls, normal positions, distance) | Examinable — univariate difference of independent normals |

**The trap that survives the exclusion:** if the weights are exponential rather than normal, the sum is **Gamma, not exponential**. That contrast (2019spB Q15 vs. 2023spA Q4) is still worth one look, and does *not* involve the Poisson–Gamma relationship.


---


---

# PART 3 — HISTORICALLY RECURRING, NOW OFFICIALLY EXCLUDED
*Retained only so that historical exam questions in `01_source_index.csv` are correctly labelled. **Do not study these. Their historical frequency must not influence your priorities.***

## Summary of what was removed and why

| Family | Excluded because | Historical footprint that is now irrelevant |
|---|---|---|
| **C — Poisson splitting / compound Poisson** | **Poisson processes are officially excluded** | Question 4 of *both* 2024 papers; 2021spB Q4; 2017spB Q5; c2adcfa6 Q4. This was the second-most-frequent construction in the modern bank — and it is now worth nothing |
| **G — MGF identification** | **MGFs are officially excluded** | 2021spA Q4; 2019spA Q10; 2019spB Q5; 2020spB-sol Q1′; 2020spA-sol Q10; 8598-sol Q9; 2017spB MGF item. Six exams |
| **L — Waiting for a pattern (HH / HT)** | Not excluded by name, but it never appeared in an open-format exam and is superseded | 2017spB Q2; 8598-sol Q8 |
| Poisson–Gamma conjugacy | **Officially excluded** | 2018wA Q14, Q15 |
| Beta-distribution posteriors | **Officially excluded** | 6637-sol ת'Q5 |
| Multivariate normal | **Officially excluded** | 2023spA Q4d; c2adcfa6 Q7; 8598-sol Q16; 2017spB Q13 |
| Borel–Cantelli; Chernoff; couplings; simulation; almost-sure convergence | **Officially excluded** | No exam question in this folder used any of them, so nothing is lost |

## Why this matters more than it looks

Before the announcement, Family C looked like a top-three priority: it carried question 4 of both 2024 papers, which is the strongest possible frequency signal from the most recent exams. Family G appeared in six separate exams. **Both are now worth zero.** This is the clearest available demonstration that recent-exam frequency is not a safe proxy for current examinability, and it is why the Core set was rebuilt from the *syllabus-as-amended* rather than from the exam bank.

The reallocated weight goes to: **Family A** (indicators and covariance), **Family D** (joint continuous densities — previously under-represented in Core), **Family B** (two-stage conditioning, now carrying the replacement Core question 2023spB Q4), and **conditional variance / the EVE law**, which is examinable, taught in T7, and has *no precedent anywhere in the exam bank* — which raises rather than lowers its expected value.

<details>
<summary>Archived detail: Family C (Poisson splitting) — click to expand</summary>

### Family C (archived)

**Recognition clues**
- `N ~ Poisson(λ)`, and then each of the `N` objects independently lands in one of several categories.
- "the number of points whose distance from the origin is at most r"
- Two counts over *nested or overlapping* regions, and you are asked for a conditional probability or a covariance between them.

**General setup**
Let `N ~ Pois(λ)`, each item independently type-A with probability p.

**Reusable solution procedure**
1. State the splitting result: `Y_A ~ Pois(λp)`, `Y_B ~ Pois(λ(1−p))`, **and Y_A ⫫ Y_B**.
2. For overlapping regions, decompose into *disjoint* regions first, then use independence between the disjoint pieces.
3. If you are asked to *derive* it: total probability over `N=n` with `Y|N=n ~ Bin(n,p)`, then the sum telescopes into a Poisson PMF.

**Variations Louidor uses**
| Variation | Where |
|---|---|
| Nested intervals [0,½] ⊂ [0,¾]; asks `P(Y_{[0,3/4]}=k | Y_{[0,1/2]}=l)` | **2024wA Q4b,c — hardest specimen** |
| Disc of radius 0.5 inside the unit disc; asks E, P(none), Cov of two overlapping counts, and E of the minimum radius | **2024wB Q4 (a–e)** |
| Unfair die rolled a Poisson number of times; asks ρ between two face-counts (answer: 0) | 2021spB Q4 — the point *is* that splitting makes them independent |
| Cars at a junction turning left/right/straight | 2017spB Q5 |
| Families arriving at a restaurant, each of random size | c2adcfa6 Q4 |

**Hidden intermediate skills**
- Computing the splitting probability geometrically (area ratio: `π(0.5)²/π = 1/4` in 2024wB Q4a).
- `Cov` between counts over *overlapping* regions: write each as a sum of disjoint-region counts and use bilinearity plus independence.
- `E(R)` for the minimum radius: tail formula `E(R) = ∫ P(R>r) dr` with `P(R>r) = e^{-λ r²}` — this is F33 order statistics **fused with** Poisson splitting (2024wB Q4e).

**Common traps**
- Assuming the counts over *overlapping* regions are independent (they are not).
- Not stating the independence of the split parts — that is the load-bearing claim.
- Forgetting the `N=0` edge case in "all points satisfy P" questions. Louidor's own 2024wB Q4c solution explicitly says both answers were accepted for the vacuous case — **so state your convention.**

**Representative questions:** 2024wB Q4 (a–e) — the whole family in one question. 2024wA Q4b,c for the nested-region conditional.

**Similar-looking but different:** 2024wA Q4a (`E(X_1+…+X_N)`) is Family B/Wald, not splitting.

**Spring 2026 status: IN CORE, with a caveat.** "Poisson process" is **not** a named topic in the Spring-2026 syllabus, and it does **not** appear in Raviv's lecture notes. However, syllabus item 18 ("sum of a random number of independent RVs") and item 7 (Poisson as an important example) make every one of these questions reachable via total probability + binomial thinning. **Practise the derivation route, not only the one-line splitting quote** — you may not be allowed to cite splitting as a named theorem.

---


</details>

<details>
<summary>Archived detail: Family G (MGF identification) — click to expand</summary>

### Family G (archived)

**Recognition clues**
- "`X` has moment generating function `M_X(t) = …`"
- The MGF is a product, a shifted exponential `e^{bt}·M(t)`, or a convex combination.

**Reusable solution procedure**
1. Compare against the MGF column of the distribution sheet.
2. `e^{bt}M_X(t)` ⟹ shift by `b`. `M_X(at)` ⟹ scale by `a`.
3. A **product** of MGFs ⟹ a sum of independent RVs.
4. A **convex combination** `p·M_1 + (1−p)·M_2` ⟹ a **mixture**: flip a coin with probability p, then draw from that distribution.
5. Answer the actual question (a probability, a moment) from the identified law.

**Variations Louidor uses**
| Variation | Where |
|---|---|
| Convex combination of two Poisson MGFs; asks `P(X=0)` | **2021spA Q4** — official solution constructs the two-stage story explicitly |
| `exp(c(e^t −1) + bt)`; asks `P(X=a)` | 2020spB-sol Q1' — shifted Poisson |
| `M_Y(t) = e^t/(1−2t)`; asks `P(Y<5 | Y≥3)` | 2019spA Q10 — shifted exponential, then memorylessness |
| Three iid two-valued RVs; asks the MGF of the sum | 2020spA-sol Q10 |
| `M_X(t) = 1/(1−t²)` for `t∈(−1,1)`; 100 iid copies, then CLT | 2017spB Q(MGF) |
| MGF of a two-stage `U ~ Unif`, `X|U ~ Exp(U)` | 2019spB Q5 |

**Common traps**
- Reading a *sum* of MGFs as a sum of RVs (it is a mixture).
- Forgetting the domain restriction on `t`.
- Not simplifying to a *named* distribution and then trying to invert the transform by hand.

**Representative questions:** 2021spA Q4, then 2019spA Q10.

**Spring 2026 status: IN CORE, but self-study.** Syllabus item 17 names MGFs. Raviv §9.8.1 covers them (7 mentions). **No Spring-2026 tutorial covers MGFs at all** — this is a genuine gap between what is examinable and what you have been drilled on.

---


</details>

<details>
<summary>Archived detail: Family L (pattern waiting) — click to expand</summary>

### Family L (archived)

**Recognition clues**
- "expected number of tosses until we first see the sequence HH / HT"

**Reusable solution procedure**
Condition on the first one or two tosses to build a small system of linear equations in the unknown expectations, then solve.

**Occurrences:** 2017spB Q2 (HT), 8598-sol Q8 (HH). Note that `E` for HT and HH **differ** (4 vs 6) — this is the classic trap and Louidor has set both versions.

**Spring 2026 status: BORDERLINE.** Reachable from conditional expectation (item 15), but it has appeared only in the multiple-choice era (2017–2018) and never in an open exam in this folder. **Variation set, not core.**

---


</details>
