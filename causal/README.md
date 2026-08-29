# Causal design reps

Prose, not code. One scenario per rep: you're handed an outcome and no ability to randomize. Write the identification strategy.

## The format

1. **The question** — what decision does this inform?
2. **Why randomization isn't available**
3. **The design** — name it: DiD, staggered adoption, synthetic control, regression discontinuity, interrupted time series, instrumental variable
4. **The comparison group** — where does the counterfactual come from?
5. **Assumptions** — what must be true, and how would you check it?
6. **Falsification** — what would you expect to see if your story is wrong?
7. **The convergent evidence stack** — no single cut proves causality; which three or four together make alternatives hard to sustain?

## The failure mode to train out

Retreating to **"we should run an experiment going forward."** That's a deferral, not an answer, and it cost the Circle round. When randomization isn't available, the job is to build a persuasive causal case from what already exists.

## Worked examples to write up

- [ ] A 2bp fee launches globally on one date; volume drops 35%. Was it the fee? *(Circle — see `Circle_HMCase_Debrief.md` for the model answer)*
- [ ] A product ships through third-party partners you can't randomize. Measure its incremental effect. *(the MIR problem — your own work; write it up formally)*
- [ ] A usage cap is introduced for all paid users at once. Measure the effect on churn. *(the GeForce NOW 100-hour cap)*
- [ ] Marketing spend rises in some regions but assignment wasn't random. Estimate incrementality.
