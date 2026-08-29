# The six patterns

Most easy–medium interview problems are one of these. **Pattern recognition is the first 30 seconds of any algorithm interview** — and it's the part that's currently weakest, so name the pattern out loud before writing any code.

Fill in your own solved examples as you go. Don't paste problem statements; paraphrase.

---

## 1. Hash-map counting

**Signal:** "how many," "most frequent," "does X appear," "find the pair that sums to."

**Idea:** trade space for time. One pass to build a dict, one pass (or the same pass) to answer. Turns an O(n²) scan into O(n).

**Tools:** `dict`, `collections.Counter`, `defaultdict(int)`, `set`

**Complexity:** O(n) time, O(n) space — say this out loud.

**Watch for:** checking membership against a *list* instead of a set (silently O(n²)); needing the index rather than the count.

**My examples:**
- *(add as you solve)*

---

## 2. Two pointers

**Signal:** sorted input, "pair that sums to," palindromes, merging two sorted things, in-place dedup.

**Idea:** two indices moving toward each other (or in the same direction) so you make one pass instead of nested loops.

**Complexity:** O(n) after sorting; O(n log n) overall if you sorted.

**Watch for:** whether the input is already sorted (if not, sorting may dominate); off-by-one on the termination condition; duplicate handling.

**My examples:**
- *(add as you solve)*

---

## 3. Sliding window

**Signal:** "contiguous subarray/substring," "longest/shortest window satisfying X," "max sum of k consecutive."

**Idea:** expand the right edge, contract the left edge when the window violates the constraint. Each element enters and leaves at most once → O(n).

**Two flavors:** fixed-size window (k given) and variable-size (grow/shrink to satisfy a condition).

**Complexity:** O(n) time; space depends on what you track in the window.

**Watch for:** forgetting to update the answer at the right moment; when to shrink vs when to record.

**My examples:**
- *(add as you solve)*

---

## 4. Sort-then-greedy

**Signal:** "minimum number of," "maximum you can schedule," "can these all fit."

**Idea:** sorting exposes structure that makes a locally optimal choice globally optimal. Most of the work is choosing the right sort key.

**Complexity:** O(n log n), dominated by the sort.

**Watch for:** justifying *why* greedy is correct here — interviewers ask. Sorting by the wrong key is the usual failure.

**My examples:**
- *(add as you solve)*

---

## 5. Heap for top-K

**Signal:** "top K," "K largest/smallest," "median of a stream," "merge K sorted lists."

**Idea:** keep a heap of size K rather than sorting everything. O(n log k) beats O(n log n) when k ≪ n.

**Tools:** `heapq.heappush`, `heappop`, `heapify`, `nlargest`/`nsmallest`

**Python gotcha:** `heapq` is a **min-heap**. For a max-heap, push negated values.

**Complexity:** O(n log k) time, O(k) space.

**Watch for:** using a min-heap for "K largest" (correct — you evict the smallest); tuple ordering when heap items are tuples.

**My examples:**
- *(add as you solve)*

---

## 6. Interval merging

**Signal:** "overlapping intervals," "meeting rooms," "free time," "insert and merge."

**Idea:** sort by start, then sweep — either merge into the previous interval or start a new one.

**Complexity:** O(n log n) for the sort, O(n) for the sweep.

**Watch for:** half-open vs closed conventions (does `[1,2]` overlap `[2,3]`?) — **ask the interviewer**; this is a legitimate clarifying question and asking it scores points.

**My examples:**
- *(add as you solve)*

---

## Lower frequency for DS roles, still worth knowing

- **BFS / DFS** — grids, trees, connected components. BFS uses a `deque`; DFS uses recursion or a stack.
- **Recursion + memoization** — know base cases and why memoization changes the complexity.
- **Light dynamic programming** — easy–medium only (climbing stairs, house robber, coin change). Diminishing returns beyond that for data-science interviews.

---

## The 30-second opener

Before writing anything:

1. Restate the problem in your own words
2. Ask a clarifying question — input size, duplicates, sorted?, edge conventions
3. **Name the pattern out loud:** "this looks like a sliding window because we want a contiguous subarray satisfying a constraint"
4. State the brute-force approach and its complexity
5. State your improved approach and its complexity
6. *Then* code

Steps 3–5 are what interviewers grade as "problem-solving." Skipping straight to code is the most common way strong candidates score badly.
