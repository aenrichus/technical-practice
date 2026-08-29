# Progress

**Phase:** 1 — Rebuild · **Started:** 2026-08-28 · **Target:** durable layer solid in 6–8 weeks

## Metrics

| Metric | Current | Target |
|---|---|---|
| LeetCode solved (easy) | 0 | 100 |
| LeetCode solved (medium) | 0 | 50 |
| Commit streak | 0 | — |
| Sessions this week | 0 | 6 |

---

## Foundations *(see `foundations/README.md`)*

**Complexity**
- [ ] Big O and the common classes
- [ ] Why dict/set lookup is O(1)
- [ ] `x in list` O(n) vs `x in set` O(1)
- [ ] List front-insert O(n) vs `deque.appendleft` O(1)
- [ ] Space complexity
- [ ] Amortized analysis
- [ ] States complexity aloud, unprompted, every problem

**Data structures**
- [ ] list · dict · set
- [ ] stack · queue/deque
- [ ] heap / `heapq` (min-heap; negate for max)
- [ ] linked list
- [ ] tree / BST traversal
- [ ] graph — adjacency list, BFS, DFS

**Python mechanics**
- [ ] Mutable vs immutable; mutable-default trap
- [ ] Comprehensions
- [ ] Generators / iterators
- [ ] `defaultdict` · `Counter` · `deque`
- [ ] Slicing, `enumerate`, `zip`, unpacking
- [ ] `sorted()` with `key=`, tuple keys, stability
- [ ] String methods, f-strings

**Sorting / searching**
- [ ] Quicksort and mergesort — how and why
- [ ] Binary search from memory, no off-by-one
- [ ] `bisect`

**The six patterns** *(see `foundations/patterns.md`)*
- [ ] Hash-map counting
- [ ] Two pointers
- [ ] Sliding window
- [ ] Sort-then-greedy
- [ ] Heap for top-K
- [ ] Interval merging
- [ ] **Names the pattern before coding, out loud**

---

## SQL
- [ ] Window functions cold: `ROW_NUMBER`, `RANK`, `DENSE_RANK`, `LAG`/`LEAD`, running totals
- [ ] Dedupe idiom automatic
- [ ] **States the grain before writing** ← already a strength, keep it
- [ ] Explains join fan-out and prevents it
- [ ] All join types **including cross join** ← the Netflix miss
- [ ] Multi-step CTEs
- [ ] Funnel and cohort/retention queries
- [ ] Asks clarifying questions on underspecified prompts

## pandas
- [ ] `groupby`/`agg`, `merge` with validation, `pivot`, `drop_duplicates`
- [ ] Rolling windows, datetimes, missing-data decisions stated aloud
- [ ] Funnel/conversion metric end to end from a raw frame

## Algorithms
- [ ] Easy in under 10 min, narrating
- [ ] Medium in under 25 min, narrating
- [ ] Complexity stated without being asked
- [ ] Pattern recognized before coding
- [ ] Edge cases aloud: empty, single, duplicates, overflow

## Statistics — spoken *(see `stats/flashcards.md`)*
- [ ] **p-value** — correct definition, cold ← failed twice at NVIDIA
- [ ] Power, Type I/II, α vs observed p
- [ ] Sample size ∝ variance ÷ effect²
- [ ] Bernoulli variance p(1−p), max at 0.5
- [ ] Parametric vs non-parametric; CLT
- [ ] **Bootstrapping** ← blanked at NVIDIA
- [ ] CUPED, multiple comparisons, MDE, CIs

## Causal
- [ ] DiD + staggered adoption — **names the method** in the MIR story
- [ ] Synthetic control vs propensity matching — distinct ← conflated at NVIDIA
- [ ] Regression discontinuity; interrupted time series
- [ ] Interference, network effects, bipartite
- [ ] Uplift vs propensity
- [ ] **Never retreats to "we should run an experiment"** ← the Circle failure

## Case structure
- [ ] Scopes in 30–60s, then signposts the framework aloud
- [ ] Metrics as numerator ÷ denominator, population, window
- [ ] Segments quantified by contribution
- [ ] **Goes one level below the framework unprompted** ← the Circle failure
- [ ] Recommendation + next step + risk, before being asked twice

## Behavioral
- [ ] Six STAR stories, ~2 min, "I"-led, quantified
- [ ] A real failure story
- [ ] A concrete mentee/team outcome ← **still blank**
- [ ] Product partnership: leads with **Meta Product Strategy Lead**, not Coursera
