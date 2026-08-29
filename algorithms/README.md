# Algorithms

Organized by **pattern**, not by problem number. See `../foundations/patterns.md`.

## Rules

- **Never commit a LeetCode problem statement.** Their terms prohibit it. Commit your solution, a one-line paraphrase, and your complexity reasoning.
- One file per problem: `solutions/<pattern>/<short-name>.py`
- Every file starts with the header block below.
- Attempt cold and timed **before** looking at any hint. A solution you looked up teaches almost nothing.

## File template

```python
"""
<short-name>
Pattern: sliding window
Paraphrase: longest substring with at most k distinct characters.

Approach: expand right, shrink left when distinct count exceeds k.
Time:  O(n) - each index enters and leaves the window once
Space: O(k) - the counter holds at most k+1 keys

Attempt 1 (2026-09-02, 14 min): got the expand right, forgot to update
the answer before shrinking. Fixed after a hint.
"""
```

The docstring is the point. **Complexity reasoning and an honest attempt note** matter more than the code.

## Targets

| Level | Time | Note |
|---|---|---|
| Easy | under 10 min | including narration |
| Medium | under 25 min | including narration |

## The 30-second opener — do this every time

1. Restate the problem
2. Ask one clarifying question
3. **Name the pattern out loud**
4. Brute force + its complexity
5. Improved approach + its complexity
6. *Then* code

Steps 3–5 are what gets graded as problem-solving. Jumping to code is how strong candidates score badly.
