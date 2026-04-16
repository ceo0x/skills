# UI Patterns & Component Standards

Match the pattern to the moment. The wrong pattern causes banner blindness (overused modals), interruption resentment (time-based tooltips), or drop-off (full-page wizards for optional tasks).

## When to Use Each Pattern

| Pattern | When to Use | When NOT to Use |
|---|---|---|
| **Full-page wizard** | Initial setup (3-5 critical steps) | After first session |
| **Persistent checklist** | Post-setup activation tasks | More than 7 items |
| **Tooltip / Hotspot** | Contextual feature discovery on first encounter | More than 2 on screen at once |
| **Modal** | Critical action or celebration only | Routine guidance (causes banner blindness) |
| **Empty state CTA** | First encounter with a blank list/dashboard | After user has created content |
| **Inline banner** | Non-blocking suggestion within a workflow | If 2+ banners already visible |
| **Slideout / Panel** | Detailed guidance needing space | Simple one-click actions |
| **Coach mark sequence** | Multi-step feature intro within a single page | More than 4 steps (use video or interactive tour) |
| **Bottom bar / Nudge** | Gentle re-engagement for incomplete checklist | If user is actively working |
| **Progress indicator** | Always, alongside steppers and checklists | Never alone — it's a companion, not a primary pattern |

## Framework-Agnostic Component Standards

Regardless of framework (React, Vue, Svelte, SwiftUI, Jetpack Compose, vanilla HTML, server-rendered), onboarding components must meet these standards.

### Onboarding Stepper
- Step indicator (progress bar showing percentage + step labels)
- Back / Next / Skip navigation with keyboard shortcuts
- Conditional steps (skip irrelevant steps based on prior answers)
- Async step support (loading state while OAuth / data import completes)
- Final step triggers celebration (confetti or platform-equivalent + specific achievement summary)
- Branching logic support for segmented flows
- State persisted across sessions

### Onboarding Checklist
- 4-6 actionable items, first one pre-checked (Endowed Progress)
- Progress ring or bar ("3 of 5 complete — almost there!")
- Each item links to its action or triggers it inline
- Items unlock sequentially or by dependency
- Estimated time per item ("~2 min")
- Celebration animation at completion
- Collapsible to floating widget after first session
- Re-expansion triggered by relevant page visits
- Dismissible but resurfaces until complete (with decreasing frequency)

### Empty State
- Illustration or icon previewing the populated state
- Headline: benefit of having content here (not "No items yet")
- Subtext: how to create the first item + time estimate
- Single primary CTA button
- Optional: "Use a template" secondary action (if Sandbox pattern applies)

### Celebration / Success
- Specific achievement data ("You connected 3 data sources in 2 minutes")
- Animation (confetti, checkmark, pulse) — respect `prefers-reduced-motion` or platform equivalent
- Clear next step CTA
- Optional social sharing for viral loops

### Tooltip / Coach Mark
- Behavior-triggered, not time-based
- Dismissible with one click
- Max 2 visible at once
- Don't stack — one finishes before next appears
- Single CTA or informational only — never multi-option

## Accessibility Requirements (Any Framework)

1. **Keyboard navigation** — all steps and actions reachable via Tab / Enter / Esc
2. **Focus management** — focus moves to the new step content when navigating
3. **Screen reader announcements** — progress updates and completion spoken
4. **Color contrast** — WCAG AA minimum for all copy
5. **Reduced motion** — respect OS/browser setting, disable confetti and heavy animation
6. **Target size** — minimum 44×44 pt touch targets on mobile

Failing these loses 5-15% of users on accessibility alone and fails compliance audits for any enterprise buyer.

## Responsive Requirements

1. **Mobile-first** — design the mobile layout first, desktop is additive
2. **Touch-friendly** — primary CTAs in thumb reach, not at the top of small screens
3. **Graceful reflow** — no horizontal scroll, no text truncation on small viewports
4. **Virtual keyboard handling** — inputs don't get covered when keyboard opens

40%+ of SaaS signups happen on mobile. A desktop-only wizard silently kills activation.

## Motion Guidelines

- **Transitions between steps** — 150-300ms ease, not longer. Slow motion feels sluggish.
- **Celebration animations** — 1-2 seconds max, skippable
- **Loading states** — if async work takes > 2 seconds, switch from spinner to progress narrative ("Syncing your data... 3 of 5 tables done")
- **Reduced motion** — always provide non-animated fallbacks; some users have vestibular sensitivity where motion causes physical discomfort
