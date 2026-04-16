# A/B Testing Playbook

Run experiments in priority order. Test the things most likely to move the needle first — waiting on marginal CTA tests while the step count is wrong wastes months.

## Tier 1 — High Impact (Test First)

These affect the entire funnel. Run one at a time to get clean signal.

1. **Number of steps** — 3 vs. 5 vs. 7 (fewer almost always wins, but test it)
2. **First action** — Which step comes first (value-first vs. config-first)
3. **Segmentation question** — With vs. without the personalization fork
4. **Social proof on signup** — Customer logos/counts vs. none
5. **Pattern choice** — e.g., Guided Wizard vs. Sandbox/Template (major pattern changes live here)

## Tier 2 — Medium Impact

These affect sections of the funnel. Can be stacked if traffic allows.

6. **Progress indicator style** — Bar vs. steps vs. percentage
7. **Checklist position** — Sidebar vs. modal vs. embedded
8. **Copy tone** — Professional vs. casual vs. urgent
9. **Celebration intensity** — Confetti vs. simple checkmark vs. data summary
10. **Email send time** — 1hr vs. 4hr vs. 24hr re-engagement
11. **Empty state CTA** — "Create your first X" vs. "Use a template" as primary

## Tier 3 — Refinement

Narrow surfaces. Don't run these until Tier 1-2 are settled.

12. **CTA copy** — "Get Started" vs. "See Your First [Value]" vs. "Create Your [Thing]"
13. **Time estimates** — Shown vs. hidden
14. **Skip option visibility** — Visible vs. hidden vs. "Do this later"
15. **Button color / micro-styling** — Rarely moves anything meaningfully

## How to Run

### Sample Size
Calculate before launching. Don't eyeball results.
- Baseline conversion × expected lift × statistical power = required sample
- Most onboarding tests need 2,000-10,000 users per variant for a 5-15% detectable lift
- If your daily signup volume is < 200, Tier 3 tests usually aren't worth running — the signal won't emerge in reasonable time

### Duration
- Minimum 2 weeks (captures weekly cycles)
- Minimum 1 full business cycle if B2B
- Don't peek and stop early — Type I error balloons with early stopping

### Success Metric
Define before the test starts. Pick one primary:
- Activation rate (most common)
- TTFV (median, not mean — mean is corrupted by outliers)
- Day-7 retention (slower signal but most meaningful)

Secondary metrics to watch:
- Step-by-step completion
- Drop-off by segment
- Downstream retention

### Stacking Rules
- Never stack Tier 1 tests — they affect the same funnel
- Tier 2 can stack with other Tier 2 if they touch different surfaces
- Tier 3 can stack freely
- If tests interact (both affect the same screen), sequence them

## What Not to Test

- **Dark patterns** — even if they lift short-term conversion, they harm LTV and trust
- **Anything without a hypothesis** — "let's see if this works" tests produce noise
- **Things you'd change regardless** — if the current version is actively broken, just fix it
- **More than 4 variants** — statistical power collapses; go sequential instead

## Reading Results

- **Practical significance > statistical significance.** A 0.3% lift with p=0.04 might be noise or might be real-but-trivial
- **Segment the results** — a test might win for power users and lose for first-timers
- **Look at time-to-activation, not just activation rate** — a flow can lift rate while slowing time (bad trade)
- **Watch for novelty effects** — new flows sometimes win because they're new, not because they're better. Re-measure after 4 weeks

## Experiment Template

Every experiment gets a 1-page spec:

```
Hypothesis: [If we do X, we expect Y to change because Z]
Primary metric: [metric + current baseline + target lift]
Secondary metrics: [watchlist]
Variants: [A / B / C]
Traffic: [% per variant]
Duration: [start date → end date, minimum 2 weeks]
Stop conditions: [safety metrics that trigger early stop]
Analysis plan: [who analyzes, when, how]
```

Every experiment gets a 1-page retrospective:

```
Result: [win / loss / inconclusive]
Effect size: [measured vs expected]
Secondary effects: [what else moved]
What we learned: [generalizable insight]
What ships: [full rollout / partial / nothing]
```

No retrospective = you didn't actually run an experiment; you just changed the product.

## Holdouts

For long-term effects (retention, LTV), keep a permanent holdout group (typically 5-10%) that never sees experiment changes. Compare their metrics to the shipped-treatment population over months. This catches slow-decaying effects that short A/B tests miss.
