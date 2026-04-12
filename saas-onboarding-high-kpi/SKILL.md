---
name: saas-onboarding-high-kpi
description: Design and build high-conversion SaaS onboarding flows with strategy, copy, checklists, UI components, and analytics instrumentation. Use when improving onboarding, increasing activation or trial-to-paid conversion, reducing time-to-first-value, or when the user mentions onboarding, activation, or TTFV.
---

# High-KPI SaaS Onboarding

Expert system for creating onboarding experiences that turn new users into active, paying users as fast as possible.

## Core Principles

1. **Value-First** — Deliver real product value before explaining features.
2. **Minimal Friction** — Core flow must be 3-7 steps maximum.
3. **Progressive Disclosure** — Show only what the user needs right now.
4. **Personalization by Intent** — Adapt the flow based on role, team size, or traffic source.
5. **Momentum & Quick Wins** — Celebrate every micro-achievement.
6. **Action-Based Guidance** — Interactive checklists beat passive "Next" tours.
7. **Continuous Onboarding** — It doesn't end after first login.

## Winning Structure

1. Welcome / post-signup screen
2. Fast authorization (OAuth / app install)
3. Minimal required configuration
4. First core action (the Aha Moment)
5. Post-activation guidance + contextual follow-ups

## Proven Patterns (Highest Converting)

- **Magic 3-Step Flow** — Authorization -> One-click Quick Setup -> Immediate first win
- **Personalized Checklist** — 4-6 actionable items with the first one pre-checked
- **Thank-You + Redirect** — Dedicated page after external trigger (great for growth loops)
- **Empty State as Opportunity** — Blank screens actively guide the user to next step

## Workflow

When asked to improve or build onboarding, always respond with:

1. **Quick diagnosis** of the current flow (or assumptions if greenfield)
2. **Proposed new flow** in 3-5 steps
3. **Ready-to-use copy and checklist templates**
4. **Expected KPI impact** (reference benchmarks in [README.md](README.md))
5. **Next A/B tests** to run

## Code Generation

When producing onboarding code, follow these rules:

### Detect the Stack

Before generating code, inspect the project for `package.json`, framework configs, or existing components. Adapt output to the user's stack (React, Vue, Svelte, plain HTML, etc.). Default to React + TypeScript if no stack is detected.

### Onboarding Stepper Component

Generate a multi-step onboarding wizard with:
- Step indicator (progress bar or numbered dots)
- Back / Next / Skip navigation
- Step completion state persisted (localStorage or backend)
- Final step triggers a celebration (confetti, success message)

### Onboarding Checklist Component

Generate an interactive checklist with:
- 4-6 actionable items, first one pre-checked
- Progress indicator (e.g., "2 of 5 complete")
- Each item links to or triggers its action inline
- Dismissible but resurfaces until all items are done

### Analytics Instrumentation

Generate event tracking for these critical moments:
- `onboarding_started` — user lands on step 1
- `onboarding_step_completed` — with `step_name` and `step_index`
- `onboarding_completed` — all steps done
- `time_to_first_value` — elapsed seconds from signup to first core action
- `onboarding_dropped_off` — with `last_step` (fire on session end or idle timeout)

Use the project's existing analytics library if detected (Segment, PostHog, Mixpanel, Amplitude, `gtag`). Otherwise produce a thin wrapper the user can plug into any provider.

### Empty State Component

When generating dashboard or list views, include an empty-state variant that:
- Shows a clear illustration or icon
- Has a headline explaining the value of the missing content
- Provides a single primary CTA to create the first item

## Anti-Patterns (Avoid at All Costs)

- Passive feature tours ("Next" x 12)
- Asking for data before delivering value
- One-size-fits-all generic flow
- Empty dashboard on first login with no guidance
- More than 10 steps
- No measurement of drop-offs

## Quick Audit Checklist

Use this to evaluate any existing onboarding:

- [ ] TTFV under 15 minutes?
- [ ] Core flow 7 steps or fewer?
- [ ] Personalization by user segment?
- [ ] Checklists actionable with quick wins?
- [ ] Guides interactive instead of passive?
- [ ] Empty states helpful and motivating?
- [ ] Drop-offs and TTFV properly instrumented?
- [ ] Micro-achievements celebrated?
- [ ] A/B tests running on key elements?
