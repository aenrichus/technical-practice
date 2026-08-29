# Stats flashcards — spoken aloud

**The bar is not "I know what that is." The bar is a correct, precise definition in 60 seconds, cold, out loud.**

This deck exists because of the NVIDIA round: the p-value was defined incorrectly twice — the interviewer asked for it a second time, which is what interviewers do when they've heard something wrong — and bootstrapping drew a blank. The concepts are all in daily use. The *spoken* version wasn't there.

**How to use:** 10 cards per session. Answer out loud before reading the answer. Anything missed goes into spaced repetition — re-test in 2 days, then 1 week, then 1 month.

---

## Inference

**Q: What is a p-value?**
The probability of observing a result **at least as extreme as the one we got, assuming the null hypothesis is true.** P(data | H₀), not P(H₀ | data).
*Not:* "the probability the result is noise." *Not:* "the probability we're wrong."
A p-value of 0.03 means: if there were truly no effect, we'd see data this extreme only 3% of the time.

**Q: Explain a p-value to a VP.**
"If this change actually did nothing, how surprising would our result be? Small p means it would rarely happen by chance, so we act. It doesn't tell us the probability we're right — for that I'd point you at the confidence interval and the effect size."

**Q: p-value vs significance level (α)?**
α is the threshold **set in advance** — the Type I error rate you'll tolerate. The p-value is what you **observe**. You compare p to α. Saying "a 5% p-value" as a standard conflates the two.

**Q: Type I vs Type II error?**
Type I (α): declaring an effect that isn't there — false positive. Type II (β): missing an effect that is there — false negative.

**Q: What is statistical power?**
1 − β. The probability of detecting a true effect **of a given size**. Power is meaningless without specifying the effect size.

**Q: The theory behind a power calculation?**
The null and alternative sampling distributions overlap. Sample size controls how tightly each concentrates. More n → narrower distributions → less overlap → you can hold α fixed and push power up. The calculation asks: given the variance, the effect worth detecting, and the error rates I'll accept, how much data do I need to separate them?

**Q: How does sample size scale?**
Roughly **variance ÷ effect size²**. Halving the MDE quadruples the required sample.

**Q: What is a confidence interval?**
A range constructed so that, under repeated sampling, 95% of such intervals would contain the true parameter. *Not* "95% probability the parameter is in this interval."

**Q: What is MDE?**
Minimum detectable effect — the smallest true effect your test is powered to detect at your chosen α and power. Set it from what's *business-meaningful*, not from what's convenient.

---

## Distributions and assumptions

**Q: For a binary metric, what's the variance and what does it imply?**
Each user is a **Bernoulli trial**; the count is **binomial**. Variance = **p(1−p)**, determined entirely by the base rate and **maximized at p = 0.5**. A metric near 50% needs the most data for the same absolute effect.

**Q: Parametric or non-parametric — how do you classify a two-proportion z-test?**
Parametric: it assumes a distributional form for the test statistic. It relies on the **Central Limit Theorem** — with large enough n, the sampling distribution of the difference in proportions is approximately normal even though the underlying data is binary. Large n *justifies* the assumption; it isn't the definition.

**Q: When do you reach for non-parametric methods?**
Small samples, heavy tails, ordinal data, or statistics with no clean closed-form variance. Mann-Whitney, permutation tests, bootstrap.

**Q: Why are revenue metrics harder than conversion metrics?**
Heavy-tailed and skewed, so variance is far larger for the same n. Remedies: winsorize or cap, log-transform, use a trimmed mean, or reduce variance with CUPED.

---

## Variance reduction and multiple testing

**Q: What is CUPED?**
Controlled experiments Using Pre-Existing Data. Use a pre-period covariate correlated with the metric to remove predictable variance, shrinking the standard error without touching the point estimate. Same power from less data.

**Q: The multiple-comparisons problem, and fixes?**
Testing many hypotheses at α = 0.05 inflates the family-wise false-positive rate. Bonferroni (divide α by the number of tests — conservative) or Benjamini-Hochberg (controls false discovery rate — usually the better choice with many metrics).

**Q: What is bootstrapping?** ← *this drew a blank at NVIDIA*
Resample your observed data **with replacement** many times (1,000–10,000), recompute the statistic each time, and use the resulting distribution as an empirical estimate of the sampling distribution. Read off standard errors and confidence intervals **without assuming normality**.
**Pros:** distribution-free; works for statistics with no closed-form variance (medians, percentiles, ratio metrics).
**Cons:** computationally expensive; unreliable in small samples; struggles at extreme quantiles; needs a cluster/block variant when observations aren't independent.
**When you'd use it:** revenue-per-user or other ratio metrics; **P90 latency or settlement time**, where there's no clean parametric standard error.

---

## Causal inference

**Q: Difference-in-differences — what does it assume?**
Compare the change in treated vs untreated over time, differencing out both fixed group differences and common time trends. The key assumption is **parallel trends**: absent treatment, both groups would have moved together. Test it by inspecting pre-period trends.

**Q: Staggered adoption / stepped wedge?**
Units adopt treatment at different times, so early adopters serve as controls for later ones. This is the **MIR** design — a product distributed through third-party measurement partners that couldn't be randomized. Note that naive two-way fixed effects can be biased with staggered timing and heterogeneous effects.

**Q: Synthetic control vs propensity score matching?** ← *conflated at NVIDIA*
**Propensity matching:** model the probability of treatment given covariates, then match or weight treated to untreated units with similar scores. Actual units to actual units.
**Synthetic control:** build a **weighted combination** of untreated units that reproduces the treated unit's *pre-treatment outcome trajectory*, and use that composite as the counterfactual. For a small number of treated aggregate units with a long pre-period.

**Q: Regression discontinuity?**
When treatment is assigned by a threshold on a running variable, units just above and just below are comparable. Estimate the jump at the cutoff. *(Example: the GeForce NOW 100-hour cap.)*

**Q: Interrupted time series?**
Model the pre-period trend and seasonality, project the counterfactual forward, and measure the gap after the intervention. Strongest when the break is sharp and time-locked to a known date.

**Q: Propensity vs uplift modeling?**
Propensity predicts **who will churn**. Uplift predicts **who is persuadable** — who changes behavior *because* of the treatment. Many at-risk users churn regardless and many stay regardless; the value is in the movable middle. Requires randomized holdouts to estimate.

**Q: What's interference, and why does it matter?**
SUTVA assumes one unit's treatment doesn't affect another's outcome. In marketplaces and social networks it does — spillover. Remedies: cluster randomization, network/graph-based assignment, bipartite designs.

**Q: No randomization is possible. What do you say?**
**Never "we should run an experiment."** Name the design: interrupted time series, dose-response across exposure levels, synthetic control, natural control series, falsification tests on unaffected segments. Then build convergent evidence — no single cut proves causality, but several consistent ones make alternatives hard to sustain.

---

## Metrics and design

**Q: How do you define a metric precisely?**
Numerator ÷ denominator, population, and time window. "Settlement success rate = settled ÷ attempted, per corridor, daily."

**Q: North-star vs input vs guardrail metrics?**
North-star: the single measure of real value. Inputs: the levers that move it. Guardrails: what must not degrade (fraud, latency, cost, cannibalization).

**Q: A key metric drops. First move?**
Confirm it's real — instrumentation and logging before theory. Then characterize the shape (step change vs drift), localize by segment, and **quantify each segment's contribution** to the total.

**Q: Sample ratio mismatch?**
Observed traffic split differs significantly from the intended split. A red flag for assignment or logging bugs. Check it before trusting any result.

**Q: Novelty and primacy effects?**
Early behavior change from newness (novelty) or resistance to change (primacy) that decays. Guard by running long enough and inspecting the effect over time rather than reading a single endpoint.
