# Technical Practice

A standing practice for keeping data-science interview skills warm — **permanently**, not just during a search.

Started 2026-08 after six interview loops in three months produced zero offers, with three late-stage losses that all traced to the same root cause: **execution and precision under time pressure, spoken aloud, without AI assistance.**

---

## Why this exists

| Loop | What broke |
|---|---|
| Circle | Asked four times to go a level below the framework; stayed high |
| NVIDIA | Defined p-value incorrectly, twice; didn't know bootstrapping |
| Netflix | SQL technical didn't clear the bar; needed help on a cross join |
| Airbnb | Algorithmic technical, failed |

The knowledge is there — the fluency isn't. Two years of AI-assisted coding did the recall, and **every technical interview banned AI tools.** That's the whole gap.

## Relationship to `interview_prep_2026`

This repo is the **durable layer**: skills that are identical across every company and should never be crammed.

The parent repo holds the **company layer** — per-company question banks, live-loop prep, and the [Reps drill app](../drill-app/) (1.4k tagged items covering SQL/Python/pandas *mechanics*, deployed at https://aenrichus.github.io/interview_prep_2026/).

**Don't duplicate the drill app.** For SQL and pandas syntax reflexes, use it. This repo covers what it doesn't:

- **Algorithms + CS foundations** — the parent `TECH_PREP_PLAN.md` deprioritized LeetCode because Circle and Zillow weren't algorithmic. Microsoft and Airbnb are. That assumption is retired.
- **Statistics spoken aloud** — the NVIDIA gap. Nothing existed for this.
- **Causal design** — written design reps.
- **The log and progress tracking** that persist across jobs.

---

## The rules

These *are* the test conditions. Practice that violates them trains the wrong skill.

1. **No AI.** No Claude, no Copilot, no autocomplete. Plain editor.
2. **Timed.** Every session.
3. **Out loud.** Narrate as if interviewing.
4. **Record one problem a week.** Watching it back surfaces filler and buried structure faster than anything else.

## Weekly rotation — ~45 min/day, six days

| Day | Focus |
|---|---|
| Mon | SQL — 3 problems, timed |
| Tue | Algorithms — 2 problems + 1 foundations topic |
| Wed | Stats aloud — 10 cards, spoken, recorded |
| Thu | SQL or pandas — alternate weeks |
| Fri | Algorithms — 2 problems + 1 foundations topic |
| Sat | Case or causal design — 1 × 20 min, out loud |
| Sun | Off, or STAR refresh |

## Phases — this outlives the job search

| Phase | When | Cadence |
|---|---|---|
| **1. Rebuild** | Now → ~8 weeks | 45 min/day, 6 days. Heavy foundations |
| **2. Search-ready** | During active loops | Same, plus company cram + extra mock |
| **3. Maintenance** | After landing | **2–3 sessions/week, ~2 hrs total** |
| **4. Refresh** | Annually, or when looking again | 2-week intensive |

Phase 3 is the point. The reason this repo starts near zero is that there was no Phase 3 last time. Scales, not cramming.

---

## Layout

```
foundations/   CS fundamentals — complexity, data structures, Python mechanics, the six patterns
algorithms/    LeetCode-style solutions, organized by pattern
stats/         spoken-aloud flashcards + written explanations
causal/        design write-ups (prose, not code)
sql/           notes and idioms (drills live in the parent drill-app)
pandas/        notes and idioms
log.md         every session: date, area, problems, time, where I stalled, fix
PROGRESS.md    competency checklist + metrics
CLAUDE.md      instructions for the Claude Code instance that runs daily sessions
```

## Committing

- **Never commit LeetCode problem statements** — it violates their terms. Commit your solution, a one-line paraphrase, and your complexity reasoning.
- **Write notes in your own words.** Explaining a concept in writing is what makes it survive an interview.
- Commit daily, even for a single problem. The contribution graph is the progress visualization.

## Metrics

1. LeetCode problems solved, by difficulty *(target: 150 easy–medium by year end)*
2. Commit streak
3. Competency boxes cleared in `PROGRESS.md`
