# 07 — Exam-ready procedures
### Revised against Prof. Louidor's official Spring 2026 announcement

**Officially confirmed format (Moed A / Moed B):** 4 open questions × 5 subparts of increasing difficulty, 5 points each, 100 points. Closed book; the official formula sheet and distribution tables are provided; a simple non-graphing calculator is allowed.

**Procedures for officially excluded families have been removed from this section** and archived in the appendix at the end. Do not work from the appendix.

One page per family. Read the recognition clues, do the "define/draw first" step **on paper before computing**, then run the procedure. The validity checks are not optional — they are how you catch the traps in `04`.

---

## Procedure 0 — The first ninety seconds of any question

**Do this before subpart (a).**

1. Read **all five subparts.** Identify what quantity (e) will need. You are allowed to use an earlier answer even if you did not derive it (2024wA rule 6).
2. Strip the story. Write one line: "n objects, property P, drawn without replacement" or "outer variable U, inner conditional law Exp(U)".
3. Name every object: `Let A = …`, `Let X = …`, `Let I_k = 1{…}`. Ambiguity here is the single largest source of lost marks.
4. Note the stated constraints (`n ≥ 2`, `α ≥ 1`, `n ≥ 3`). They are there because a step later requires them.
5. Decide the format of the final answer: a number, a closed form, a named distribution with parameters. You may give a distribution as a PMF, density, CDF, **or name+parameters**. *(Earlier papers also allowed an MGF; with MGFs excluded this semester, that option is no longer available to you.)*

**Time discipline.** Four questions, three hours ⟹ ~40 minutes each with 20 minutes spare. Subparts get harder within a question (2024wA rule 5 says so explicitly). If a subpart has eaten 12 minutes, move on and come back.

---

## Procedure A — Count objects: expectation by indicators, variance by covariance

**Recognition clues**
"Expected number of…" immediately followed by "variance of…". The counted objects overlap: share a row, a vertex, a pool, a neighbour.

**Define first**
`I_k = 1{object k has property P}`, `k = 1..N`. Write the index range. Write `X = Σ I_k`.

**Procedure**
1. `E(I_k) = P(A_k)`. Compute `P(A_1)` once.
2. `E(X) = N·P(A_1)` by linearity **and symmetry**. Write "linearity does not require independence."
3. `E(X²) = Σ_k P(A_k) + Σ_{k≠j} P(A_k ∩ A_j)`.
4. **Classify the ordered pairs `(k,j)`, `k≠j`, by their overlap type.** For each class: how many pairs, and what is `P(A_k ∩ A_j)`?
5. `Var(X) = E(X²) − E(X)²`.

**Required assumptions**
Only that the indicators are well defined. Independence is *not* needed and usually false.

**Validity checks**
- `Var(X) ≥ 0`.
- If you set every dependence to zero, do you recover the binomial `Np(1−p)`? If not, recheck the overlap counting.
- The pair counts must sum to `N(N−1)` (ordered) — verify this arithmetically.
- Degenerate parameter values (e.g. `k > 2^{n−1}` in 2024wA Q1c) should give 0 or 1, not nonsense.

**Common mistake**
Dropping the covariance terms. Or writing `Σ_{k<j}` while counting `N(N−1)` pairs.

**Best representative questions:** 2024wA Q1d,e (three overlap classes) · 2021spA Q7a,b (graph overlaps) · 2023spA Q2b,c.

---

## Procedure B — Two-stage experiment: condition, then smooth

**Recognition clues**
"First draw N, then…". "The rate is itself random." A conditional law is handed to you.

**Define first**
Write the two lines: `Y ~ (outer law)` and `X | Y=y ~ (inner law with parameter θ(y))`.

**Procedure**
1. From the table: `E(X|Y=y) = g(y)`. Emphasise that `E(X|Y) = g(Y)` is a **random variable**.
2. `E(X) = E(g(Y))` — tower law. Compute the outer expectation.
3. For a distribution: `F_X(t) = ∫ P(X≤t | Y=y) f_Y(y) dy` (continuous outer) or `Σ P(X≤t|Y=n)P(Y=n)` (discrete outer).
4. Differentiate to get `f_X`.
5. For the posterior on the parameter: `f_{Y|A}(y) = P(A|Y=y)·f_Y(y) / P(A)` where `P(A)` came from step 3.
6. If the inner variables are summed a random number of times: `E(S) = E(N)·E(X_1)` (Wald), valid because `N ⫫ X_i`.

**The latent-normal branch (new Core question 2023spB Q4)**
When the outer variable is `X ~ N(0,1)` and the inner law is `Y | X=x ~ N(x,1)`:

6. Marginal: `f_Y(y) = ∫ f_{Y|X}(y|x) f_X(x) dx`. Multiply the two kernels, collect the exponent as a **quadratic in `x`**, and **complete the square in `x`**. The integral of the completed square is a normal density and equals 1; the leftover `y`-dependent prefactor *is* `f_Y(y)`. → `Y ~ N(0,2)`.
7. Posterior: `f_{X|Y}(x|y) = f_{Y|X}(y|x) f_X(x) / f_Y(y)`. Complete the square in `x` again. → `X | Y=y ~ N(y/2, 1/2)`.
8. Prediction for a *second* observation: use **conditional independence**, `E(Y₂ | Y₁=y, X=x) = E(Y₂ | X=x) = x`, then smooth over the **posterior** of `X` given `Y₁=y`, not over its prior. → `E(Y₂|Y₁=y) = E(X|Y₁=y) = y/2`.

**Required assumptions**
`N` independent of the `X_i` for Wald. The inner law must be stated for *every* value of the outer variable. For step 8, the observations must be independent *given* the latent variable — check that the question says so (2023spB Q4 states it via an explicit product form).

**Validity checks**
- `∫ f_X = 1`.
- Does `E(X)` from the tower law match a direct computation in a special case (e.g. degenerate `Y`)?
- The posterior must integrate to 1 over the support of `Y` — and that support is unchanged by conditioning.

**Common mistake**
Using the discrete total-probability formula when the outer variable is continuous. Treating `E(X|Y)` as a number. In the latent-normal branch: answering `E(Y₂|Y₁=y) = 0` because you treated `Y₁` and `Y₂` as unconditionally independent, or smoothing over the prior instead of the posterior.

**Best representative questions:** **2023spA Q3a–e** (uniform outer, exponential inner — the forward-then-posterior direction) and **2023spB Q4a–e** (normal latent variable — the completing-the-square direction). **2024wA Q4(a) only** is a usable random-sum drill; subparts (b)–(e) of that question are excluded.

---

## Procedure D — Joint continuous distributions

**Recognition clues**
A joint density with a constraint: `0<x<y<∞`, `|x|<y`, "uniform on the triangle with vertices…". Any request for a marginal, a conditional, or `P(region)`.

**Draw first**
**Sketch the support in the (x,y) plane.** Label each bounding line with its equation. This is not optional — the official solution to c2adcfa6 Q1 recommends it in writing.

**Procedure**
1. Normalisation: `∫∫_S f = 1` ⟹ solve for `c`.
2. **Before integrating, try to pattern-match**: does `f(x,y)` factor into `f_X(x)·f_{Y|X}(y|x)` with both factors standard? (Gamma × Uniform is Louidor's favourite.) If yes, read off the answer.
3. Marginal of `X`: fix `x`, read the `y`-range off the sketch, integrate. **The limits depend on `x`.**
4. Conditional: `f_{Y|X}(y|x) = f(x,y)/f_X(x)`, valid on the `x`-dependent support.
5. `P(region)`: intersect the region with `S`. Fix the outer variable, read the inner range, split into cases wherever the boundary description changes.
6. Independence: requires factorisation **and** a rectangular (product) support.

**Required assumptions**
`f ≥ 0` on `S`, integrable.

**Validity checks**
- `∫ f_X(x) dx = 1`.
- `∫ f_{Y|X}(y|x) dy = 1` **for every** `x` in the support.
- `E(Y) = E(E(Y|X))` computed both ways should agree.
- If the support is a triangle, `X` and `Y` cannot be independent, whatever the algebra suggests.

**Common mistake**
Integrating `x` from `0` to `∞` when `x < y` binds. Forgetting the conditional support depends on `x`.

**Best representative questions:** 2020spB-sol Q2,Q2′ · c2adcfa6 Q1 · 2020spA-sol Q12.

---

## Procedure E — Transformations and convolution

**Recognition clues**
"Find the density of `Y = g(X)`". `Z = X ± Y`. Anything with `min`, `max`, `floor`, `mod`, or a piecewise definition.

**Define first**
Write the range of `Y`. Sketch `g` if it is not monotone.

**Procedure**
1. Start from `F_Y(y) = P(Y ≤ y)` and **rewrite the event in terms of `X`**. Never guess the density.
2. Identify the `y`-intervals on which the rewritten event changes form. You will get a piecewise `F_Y`.
3. Differentiate on each piece. State the support.
4. Non-monotone `g`: split the domain of `X` into monotone pieces and add the contributions.
5. Sum of independents: `f_Z(z) = ∫ f_X(x) f_Y(z−x) dx`. **Write both indicator constraints, intersect them, and let that determine the limits.**
6. Mod-1 wrap: `Z = S mod 1` means `f_Z(z) = f_S(z) + f_S(z+1)` for `z ∈ [0,1)` when `S ∈ [0,2)`.

**Required assumptions**
Independence for convolution. Differentiability of `F_Y` (except at finitely many points).

**Validity checks**
- `∫ f_Y = 1` — the single most useful check in this family.
- `f_Y ≥ 0` everywhere.
- `F_Y` is continuous and non-decreasing; `F_Y(−∞)=0`, `F_Y(∞)=1`.
- Test a special value you can compute directly (e.g. `P(X ≤ 1)` in 2024wB Q2a should equal ½ by symmetry).

**Common mistake**
Differentiating before restricting to the support. Convolving without intersecting supports.

**Best representative questions:** 2024wB Q2a–e · 2018wA Q7 · 2020spA-sol Q8.

---

## Procedure F — Maxima, minima and order statistics

**Recognition clues**
"the largest / smallest of n independent…", `X_(k)`, "the closest point", `X = min(U₁,U₂)` and `Y = max(U₁,U₂)`.

**Define first**
Write `Z_1,…,Z_n` for the underlying iid variables and their common CDF `F`.

**Procedure**
1. `P(max ≤ x) = F(x)^n`.
2. `P(min > x) = (1 − F(x))^n`, so `P(min ≤ x) = 1 − (1−F(x))^n`.
3. Joint: `P(max ≤ x, min ≤ y) = P(max ≤ x) − P(max ≤ x, min > y)`, and `P(max≤x, min>y) = (F(x) − F(y))^n` **when `x ≥ y`**, else 0.
4. Discrete PMF: `P(X = x) = P(X≤x) − P(X≤x−1)`.
5. Joint discrete PMF from a joint CDF, four corners:
   `P(X=x, Y=y) = F(x,y) − F(x−1,y) − F(x,y−1) + F(x−1,y−1)`.
6. `X_(k)`: "exactly `k−1` of the `n` fall below `c`" → Binomial.
7. Useful identity: `max(a,b) = a + b − min(a,b)`, so `E(max) = E(a)+E(b)−E(min)`.
8. `min` of independent `Exp(λ_i)` is `Exp(Σλ_i)`.

**Required assumptions**
Independence throughout. Identical distribution for the power formulas (otherwise take a product of different `F_i`).

**Validity checks**
- `P(max ≤ x) ≤ P(min ≤ x)` for every `x`.
- The joint PMF must sum to 1 over the grid.
- For `n = 1`, max = min = the variable itself — substitute and check.
- The joint CDF must be non-decreasing in each argument.

**Common mistake**
Off-by-one in the discrete case. Sign errors in the four-corner conversion. Applying the product formula without independence.

**Best representative questions:** 2024wB Q1a–e · 2019spA Q11 · 2024wB Q4e.

---

## Procedure H — Inequalities and convergence in probability

**Recognition clues**
"Bound from above/below…". "Show that `X_n` converges weakly / in probability to `L`", with the ε-definition supplied as a reminder.

**Define first**
Write `μ_n = E(X_n)` and `σ_n² = Var(X_n)` explicitly. You will need both.

**Excluded from this family this semester:** the **Chernoff bound**, and **almost-sure convergence / the strong law of large numbers**. Markov, Chebyshev, the *weak* law, convergence *in probability* and the CLT are all examinable and are what follows.

**Procedure — Markov**
1. Make the variable non-negative. If it can be negative, use `|X − c|^n` or `X²`.
2. `P(W ≥ a) ≤ E(W)/a` for `W ≥ 0`.
3. For a *lower* bound on `P(W ≤ a)`, take the complement: `P(W ≤ a) = 1 − P(W > a) ≥ 1 − E(W)/a`.

**Procedure — Chebyshev**
1. `P(|X − μ| ≥ ε) ≤ σ²/ε²`.
2. **Check whether the bound exceeds 1.** If it does, say so — this is a legitimate answer and Louidor has asked for it deliberately (2023spB Q2d).

**Procedure — convergence in probability**
1. Compute `μ_n` and `σ_n²`.
2. Show `σ_n² → 0` and `μ_n → L`.
3. Triangle inequality: `|X_n − L| ≤ |X_n − μ_n| + |μ_n − L|`.
4. Hence `{|X_n − L| > ε} ⊆ {|X_n − μ_n| > ε/2} ∪ {|μ_n − L| > ε/2}`.
5. Union bound: `P(|X_n−L|>ε) ≤ P(|X_n−μ_n|>ε/2) + P(|μ_n−L|>ε/2)`.
6. Chebyshev on the first: `≤ σ_n²/(ε/2)² → 0`. The second is a deterministic sequence that is eventually 0.
7. Since probabilities are non-negative, the limit is exactly 0.

**Alternative route (2023spB Q2e, accepted):** if `X_n = h(Y_n)` with `h` continuous at the limit and `Y_n → c` by the WLLN, then `X_n → h(c)`.

**Procedure — CLT**
1. Write `S_n = Σ X_k`, `μ = E(X_1)`, `σ² = Var(X_1)`.
2. Standardise: `(S_n − nμ)/(σ√n) ≈ N(0,1)`.
3. Rewrite the target event in terms of the standardised variable.
4. `P(a ≤ Z ≤ b) ≈ Φ(b) − Φ(a)`. For a symmetric interval, `2Φ(c) − 1`.

**Validity checks**
- A Markov or Chebyshev bound greater than 1 is correct but vacuous — say so.
- A Chebyshev bound must shrink as `n` grows if you are proving convergence.
- CLT: `σ√n`, not `σ`. Recompute `Var(X_1)` if your answer looks implausible.
- A probability must lie in [0,1].

**Common mistake**
Chebyshev applied to `|X_n − L|` when `E(X_n) ≠ L`. Standardising with the wrong scale.

**Best representative questions:** 2023spA Q2e · 2023spB Q2d,e · 2024wA Q2e · 2021spB Q6b,c.

---

## Procedure I — Recursive / self-referential probability

**Recognition clues**
"In any other case, continue to another round — with only the players who…". The game can return to its starting state.

**Define first**
`A` = the event you want. Write `P(A) = p` as an unknown.

**Procedure**
1. Condition on the **first round only**.
2. Enumerate the outcomes of the first round with their probabilities.
3. For each outcome, classify: (i) the game ends with `A`, (ii) the game ends without `A`, (iii) it reduces to a smaller case you have already solved, (iv) it returns to the original problem.
4. Total probability: `p = Σ P(outcome)·P(A | outcome)`, where the type-(iv) branches contribute `c·p`.
5. Solve the linear equation.

**Required assumptions**
Independence across rounds, and that the process really is memoryless in state.

**Validity checks**
- `p ∈ [0,1]`.
- Test a degenerate parameter (e.g. `n=1`) against direct reasoning.
- Verify your outcome probabilities sum to 1 before conditioning.

**Common mistake**
Missing the "everyone eliminated" absorbing branch. Summing an infinite series when one equation would do.

**Best representative question:** 2023spA Q1e.

---

## Procedure J — Sequential draws with a changing urn

**Recognition clues**
Without replacement; or with replacement but the drawn object is modified. "Given that the first `k−1` draws were black…"

**Define first**
Write the urn composition **as a function of the step index**.

**Procedure**
1. Chain rule: `P(A_1 ∩ … ∩ A_n) = P(A_1)·P(A_2|A_1)···P(A_n|A_1,…,A_{n−1})`.
2. Write each conditional using the composition at that step.
3. For "the `k`-th draw has property P", first try **symmetry** (all positions exchangeable). If the process is not exchangeable, try the **tagged-object** reframing: pick one specific object and ask about *its* history.
4. For "time until all objects are converted", decompose into a sum of independent geometrics with changing success probability, then use linearity.

**Required assumptions**
Each draw uniform over what remains. Independence of draws *given* the current composition.

**Validity checks**
- Probabilities at each step must be in [0,1] and the composition counts must stay non-negative.
- Check `n = 1` and `n = 2` by hand.
- In "expected time to absorb" problems, the answer must be increasing in `n`.

**Common mistake**
Using a fixed probability when the composition changes. Wrong index range in the coupon-collector sum.

**Best representative questions:** 2024wB Q3a–e · 2021spA Q5 · 2023spB Q3.

---

## Procedure K — Normal vectors and shared-component covariance

**Recognition clues**
Independent normal weights summed along overlapping paths; "find the joint distribution of `X_i` and `X_j`".

**Define first**
Write each target quantity as an **explicit linear combination** of the underlying independent variables, with named indices.

**Procedure**
1. `E` by linearity.
2. `Var` by independence: `Var(Σ a_k W_k) = Σ a_k² Var(W_k)`.
3. `Cov(Σ a_k W_k, Σ b_m W_m) = Σ_k a_k b_k Var(W_k)` — only the **shared** components survive.
4. Translate the structural description (graph distance, shared rows) into a count of shared components.
5. ~~A linear image of a jointly-normal vector is jointly normal ⟹ write `N(mean vector, covariance matrix)`.~~ **EXCLUDED — the multivariate normal distribution is not on the Spring 2026 exam. Do not perform this step. If a question asks for the *joint* distribution of two correlated normals, that subpart is out of scope (this is exactly 2023spA Q4d, which you are told to skip).**
6. `ρ = Cov/(σ_X σ_Y)`.
7. For the *univariate* distribution of a single linear combination of independent normals (e.g. the total weight over all leaves), the sum is normal with the summed mean and summed variance — **this remains examinable** and is 2023spA Q4(e).

**Required assumptions**
The underlying variables are independent. (Steps 1–4, 6 and 7 need only independence and finite variances; they do not require any multivariate-normal theory.)

**Validity checks**
- `|ρ| ≤ 1`. If not, you have over- or under-counted shared components.
- Setting the two objects equal must give `Cov = Var`.
- The shared-component count must be an integer between 0 and the path length.
- **If the weights are exponential rather than normal, the sum is Gamma, not exponential** — do not carry the normal conclusion across.

**Common mistake**
Adding standard deviations. Assuming a sum of independent non-normals stays in the same family.

**Best representative questions:** **2023spA Q4 subparts (a), (b), (c) and (e)** — *skip (d)*. 2019spB Q15 is the same skeleton with exponential weights and is a useful contrast, but it is a multiple-choice item and redundant once (a)–(c) and (e) are secure.

**Family status: MIXED.** Four of the five subparts of its best specimen survive; only the joint-normal step is out of scope.

---
---

# APPENDIX — Archived procedures for officially excluded families

**Do not work from this appendix.** These procedures are retained only so that historical exam questions in `01_source_index.csv` can be read and correctly labelled. Each family below is **officially excluded from the Spring 2026 exam**.

<details>
<summary><strong>ARCHIVED — Poisson splitting and compound Poisson</strong> (excluded: Poisson processes)</summary>

Historical footprint: question 4 of *both* 2024 papers, 2021spB Q4, 2017spB Q5, c2adcfa6 Q4. This was the second-most-frequent construction in the modern bank and is now worth nothing for your preparation.

**One carve-out.** `E(X_1 + … + X_N)` for a random `N` independent of the summands is **Wald's identity / sum of a random number of independent RVs**, syllabus item 18, and remains **examinable**. It is covered by Procedure B steps 1–6 and does not require any Poisson-process theory. The isolated drill is 2024wA Q4(a).

#### Archived procedure text

**Recognition clues**
`N ~ Pois(λ)`, then each of the `N` items independently falls into a category. Two counts over nested or overlapping regions.

**Define first**
Draw the regions. Write `p = P(one item is type A)` — usually a length, area, or volume ratio.

**Procedure**
1. **Decompose into disjoint regions.** Nested regions are *not* independent; disjoint ones are.
2. State: `Y_A ~ Pois(λp)`, `Y_B ~ Pois(λ(1−p))`, and `Y_A ⫫ Y_B`.
3. Overlapping counts: write each as a sum of disjoint-region counts, then use bilinearity of covariance and independence.
4. **If you are not sure splitting may be quoted, derive it:** `P(Y=y) = Σ_{n≥y} C(n,y)p^y(1−p)^{n−y}·e^{−λ}λ^n/n!`, factor out `e^{−λ}(λp)^y/y!`, and the remaining sum is `e^{λ(1−p)}`.
5. Edge case: decide and **state** your convention for `N = 0` in "all items satisfy P" questions.

**Required assumptions**
`N` Poisson; item categories independent of each other and of `N`.

**Validity checks**
- Poisson parameters of the parts must sum to `λ`.
- A covariance between counts over *disjoint* regions must be 0; between *nested* regions it must be positive.
- Any probability you get must be in [0,1] for all `λ > 0`.

**Common mistake**
Treating overlapping counts as independent. Failing to state the independence of the split parts, which is the load-bearing claim.

**Best representative questions:** 2024wB Q4a–e · 2024wA Q4b,c · 2021spB Q4.

---

</details>

<details>
<summary><strong>ARCHIVED — MGF identification</strong> (excluded: moment generating functions)</summary>

Historical footprint: 2021spA Q4, 2019spA Q10, 2019spB Q5, 2020spB-sol Q1′, 2020spA-sol Q10, 8598-sol Q9, 2017spB MGF item. Six separate exams.

**Note on the distribution sheet.** The official distribution tables provided in the exam contain an MGF column. Ignore it. **Note on the answer-format rule.** Earlier papers allowed a distribution to be given as an MGF; that option is not available to you.

#### Archived procedure text

**Recognition clues**
"X has moment generating function…". Products, `e^{bt}` prefactors, or convex combinations.

**Define first**
Have the MGF column of the distribution sheet open.

**Procedure**
1. Strip a prefactor: `M_X(t) = e^{bt}M_Y(t)` ⟹ `X = Y + b`.
2. Strip a scale: `M_X(t) = M_Y(at)` ⟹ `X = aY`.
3. A **product** `M_1(t)·M_2(t)` ⟹ `X = Y_1 + Y_2` with `Y_1 ⫫ Y_2`.
4. A **convex combination** `pM_1 + (1−p)M_2` ⟹ a **mixture**: with probability `p` draw from law 1, else from law 2.
5. Identify the base law by matching against the table.
6. Answer the actual question from the identified law (a probability, a moment, a conditional probability).

**Required assumptions**
The MGF determines the distribution uniquely (state this — it is the theorem you are using).

**Validity checks**
- `M_X(0) = 1`.
- `M_X'(0) = E(X)`, `M_X''(0) = E(X²)` — differentiate and check against the identified law's known moments.
- The domain restriction on `t` must match the identified law (e.g. `t < λ` for exponential).

**Common mistake**
Reading a *sum* of MGFs as a sum of RVs. Forgetting the domain restriction.

**Best representative questions:** 2021spA Q4 · 2019spA Q10 · 2020spB-sol Q1′.

---

</details>

<details>
<summary><strong>ARCHIVED — other excluded topics with no procedure</strong></summary>

The following are officially excluded and had **no** representative in this folder, so no procedure was ever written and nothing is lost: **simulation**, **couplings**, **Borel–Cantelli lemmas**, **the Chernoff bound**, **almost-sure convergence / the strong law**.

Two further exclusions removed individual questions rather than whole families:
- **Poisson–Gamma relationship** → 2018wA Q14, Q15.
- **Beta distribution** → 6637-sol ת'Q5.
- **Multivariate normal** → 2023spA Q4(d), c2adcfa6 Q7, 8598-sol Q16, 2017spB Q13. See Procedure K, step 5.

</details>
