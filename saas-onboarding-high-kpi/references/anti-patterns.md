# Anti-Patterns

Avoiding these is worth more than optimizing any individual component. Each anti-pattern represents a specific user-hostile pattern that predictably kills retention or conversion.

| Anti-Pattern | Why It Kills KPIs | What to Do Instead |
|---|---|---|
| Passive feature tour ("Next" × 12) | 70-90% drop-off by step 5. Users aren't learning — they're swiping. | Interactive actions that produce real results. One feature per tour max. |
| Asking for data before showing value | Feels like a tax, not an investment. Users haven't committed yet. | Deliver a quick win first, then ask. |
| One-size-fits-all flow | Irrelevant steps cause abandonment. Users with the wrong needs disengage. | Segment by 1-2 dimensions. |
| Empty dashboard on first login | Blank-slate paralysis. No obvious next action. | Template, demo data, or a guided first action. |
| > 7 steps in initial wizard | Completion drops ~15% per step beyond 5. Compound loss. | Defer non-essential config to post-setup checklist. |
| Time-based tooltips | Interrupts flow, creates resentment. User was focused, now they're not. | Behavior-triggered contextual guidance. |
| Mandatory email verification before value | 30-50% never verify, never activate. Verification becomes the drop-off. | Allow limited use pre-verification; verify before export/share/payment. |
| "Watch this 3-min video" as step 1 | Passive, not personalized, often skipped — and users still don't know what to do. | Interactive quickstart with same content, embedded in the actual UI. |
| Requiring team invite before solo value | Blocks activation on external dependency. If teammate doesn't join, user churns. | Show solo value first. Invite as amplification, not gate. |
| No measurement | Can't improve what you can't see. Decisions become opinion battles. | Instrument before redesigning. |
| Walls of text | Users don't read. 3+ lines of copy per screen is 2 too many. | 1 headline, 1 subheadline, 1 CTA. Use visuals for the rest. |
| Multiple simultaneous modals | Banner blindness sets in. Users reflexively dismiss. | Max 1 modal at a time. Queue others. |
| Fake progress bars | Users notice when the bar jumps or stalls. Trust dies. | Real progress based on actual completion. If async, show stages. |
| "Almost done!" on step 1 | Same trust issue — users know what "almost" feels like. | Accurate framing: "4 quick steps" beats "almost done!" on step 1. |
| Forced signup on mobile first-open | Mobile users bounce 40-60%+ when signup is the first screen. | Let them see value first. Deferred sign-in or guest mode. |
| Requesting all permissions on launch (mobile) | Declines compound. iOS only lets you ask push once. | Permissions at moment of need, with pre-prompt context. |
| No skip option | Triggers app-review rejection and user rage. | Always offer skip, with "You can do this later" framing. |
| Gated tutorial the user can't exit | Hostile. Users install → uninstall. | Skippable coach marks. Return-visit tutorials for users who want them. |
| Confetti on every minor action | Celebration inflation. Stops feeling like a reward. | Save big celebrations for Aha Moment and milestone completions. |
| Surprise paywall mid-flow | Bait-and-switch feeling. Trust crater. | Show pricing upfront. Trial gates are fine if communicated early. |
| "Thanks for signing up! Here's 20 emails." | Spam-shaped welcome. Unsubscribe rate spikes. | One welcome email with a clear next step. Additional emails trigger-based. |
| Copy that pretends to be personal when it isn't | "Hey friend!" from a no-reply address is worse than no personalization. | Either truly personal (founder reply-to) or don't pretend. |
| CAPTCHA during signup | 10-30% drop rate, users hate it. | Use invisible risk scoring; only challenge suspicious signups. |
| Session timeout mid-onboarding | Users lose all progress, abandon. | Persist state. Long session tokens during onboarding. |
| Asking "Why did you sign up?" as step 1 | User doesn't know yet — they're evaluating. | Ask after Aha Moment, when they have context to answer. |

## The Meta Anti-Pattern

**Optimizing onboarding without knowing your Aha Moment.** Every anti-pattern above assumes you know what retention-driving action you're driving users toward. If you don't, fix that first (see `aha-moments.md`). Otherwise you're optimizing a path to an unknown destination.
