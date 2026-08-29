# Foundations — the CS layer

**Why this exists:** you learned Python as a tool for analysis, not as a discipline. That's normal for a PhD-trained scientist and it's invisible until an interviewer asks for the complexity of your solution, or hands you a problem that wants a heap.

**Do these in order.** The patterns don't make sense without complexity and data structures underneath.

Roughly 4–6 weeks at one topic per algorithms day (Tue/Fri). Write each topic up in your own words as you go — that's what makes it stick.

---

## Week 1–2 — Complexity

- [ ] Big O: what it measures, and what it deliberately ignores
- [ ] The common classes and what they feel like at scale: O(1), O(log n), O(n), O(n log n), O(n²), O(2ⁿ)
- [ ] **Why dict/set lookup is O(1)** — hashing, buckets, collisions
- [ ] Why `x in my_list` is O(n) but `x in my_set` is O(1) *(this alone fixes a lot of interview code)*
- [ ] Why inserting at the front of a list is O(n), and why `deque.appendleft` is O(1)
- [ ] Space complexity — and why it's the follow-up question when you've nailed time
- [ ] Amortized analysis: why `list.append` is O(1) despite resizing
- [ ] **Practice: state time and space complexity out loud for every function you write.** Unprompted, every time.

→ write up `complexity.md`

## Week 2–3 — Data structures

- [ ] **Array / list** — indexing, append, insert, the cost of each
- [ ] **Hash map / dict** — the workhorse; counting, grouping, lookup, `defaultdict`, `Counter`
- [ ] **Set** — dedup, membership, set algebra
- [ ] **Stack** — LIFO; a plain list is fine; matching-parens and undo patterns
- [ ] **Queue / deque** — FIFO; `collections.deque`; BFS
- [ ] **Heap / priority queue** — `heapq`, top-K, streaming median. *Python's heapq is a min-heap; negate for max*
- [ ] **Linked list** — understand pointers and traversal. Rare in DS interviews; don't over-invest
- [ ] **Tree / BST** — traversal (in/pre/post-order), depth, BFS by level
- [ ] **Graph** — adjacency list, BFS, DFS, visited sets

→ write up `data-structures.md`

## Week 3–4 — Python mechanics

- [ ] Mutable vs immutable; pass-by-object-reference
- [ ] **The mutable default argument trap** (`def f(x, acc=[])`)
- [ ] List / dict / set comprehensions; when a loop is clearer
- [ ] Generators and iterators; `yield`; when laziness matters
- [ ] `collections`: `defaultdict`, `Counter`, `deque`
- [ ] Slicing semantics, negative indices, `[::-1]`
- [ ] `enumerate`, `zip`, unpacking
- [ ] `sorted()` vs `.sort()`; the `key=` argument; tuple keys; stability
- [ ] String methods, `join`/`split`, f-strings
- [ ] Truthiness, `is` vs `==`, `None` handling

→ write up `python-mechanics.md`

## Week 4–5 — Sorting and searching

- [ ] How quicksort works; average vs worst case
- [ ] How mergesort works; why it's stable and O(n log n) guaranteed
- [ ] Why Python's `sorted()` (Timsort) is what you should almost always use
- [ ] **Binary search** — and the off-by-one traps. Write it correctly from memory
- [ ] `bisect` module
- [ ] Sorting as a preprocessing step — the setup for two pointers and greedy

→ add to `data-structures.md` or its own file

## Week 5–6 — The six patterns

See `patterns.md`. These cover most easy–medium problems:

- [ ] Hash-map counting
- [ ] Two pointers
- [ ] Sliding window
- [ ] Sort-then-greedy
- [ ] Heap for top-K
- [ ] Interval merging

Plus, worth knowing but lower frequency for DS roles: BFS/DFS, recursion + memoization, light DP.

---

## The bar

You've finished foundations when you can, cold and out loud:

1. State the complexity of any function you just wrote, without being asked
2. Name which pattern a problem needs **before** writing code
3. Explain why a dict is O(1) and a list scan is O(n) to a non-expert
4. Reach for `Counter`, `defaultdict`, `deque`, or `heapq` without looking them up
