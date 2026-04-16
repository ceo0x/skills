# Discovery Questionnaire

Before proposing any design changes, establish the context. Ask the user these questions — not all at once, but woven into the conversation. Skip ones the user has already answered or that aren't relevant.

## Product Context

1. **What does your product do?** (one sentence, plain language — not marketing copy)
2. **Who's the primary user?** (role, team size, technical sophistication)
3. **Is there more than one distinct persona?** If yes, which are we optimizing for in this pass?
4. **Is this B2B, B2C, or B2B2C?**
5. **Self-serve, sales-led, or hybrid?**
6. **Primary platform: web, mobile (iOS/Android), desktop app, API/CLI, or multi-platform?**

## Current State

7. **Do you have onboarding now? If yes, what does it look like?** (ask for a walkthrough, screenshots, or link)
8. **What analytics do you have in place? What events fire?**
9. **What's your current TTFV, activation rate, and trial-to-paid conversion (if applicable)?** If they don't know, that's itself a finding.
10. **Where's the biggest drop-off in your funnel today?**

## Aha Moment

11. **What's your Aha Moment — the single action most correlated with retention?** If they don't know, note it and plan to run the identification methodology (see `aha-moments.md`).
12. **How long does it currently take a new user to reach it?**
13. **What's blocking users from getting there faster today?**

## Business Context

14. **What's the primary metric you're trying to move?** (activation rate, TTFV, trial-to-paid, day-30 retention — pick one to prioritize)
15. **What's the target, and by when?**
16. **What's the cost of a failed activation?** (especially for high-ACV or regulated products)
17. **Are there constraints you can't change?** (compliance steps, legacy systems, external approvals)

## Stack & Capacity

18. **What's your tech stack?** (framework, analytics provider, email provider — informs what code/events to generate)
19. **Who builds it?** (team size, time budget — informs scope of recommendations)
20. **Is there an existing component library or design system to match?**

## Segmentation

21. **Do you have distinct user segments with different optimal flows?** If yes, which 1-2 dimensions matter most?
22. **What do you know about users at signup?** (UTM, referral source, email domain, device — what can you infer vs must you ask?)

## Multi-Channel

23. **Do you have an email sequence for new users? What triggers it and sends it?**
24. **Do you have human touchpoints — founder email, CS outreach, concierge?**
25. **For high-value accounts, is there an ICP definition and routing to sales?**

## Edge Cases

26. **Does your product have unavoidable latency in delivering value?** (compliance scans, data accumulation, third-party approval)
27. **Any regulated onboarding steps?** (KYC, HIPAA, age, GDPR)
28. **Mobile-specific: do you handle permission prompts and push opt-in deliberately?**

## When to Stop Asking

If the user is time-boxed, ask the minimum set:
- #1, #5, #6 (product basics)
- #11, #12 (Aha Moment)
- #14 (primary metric)
- #18 (stack)

Everything else can be inferred or deferred. The purpose of discovery is to prevent the #1 failure mode: designing the wrong onboarding for a product you don't understand.

## Output of Discovery

After discovery, you should be able to write a 3-4 sentence context summary:

> "[Product] is a [category] for [user]. They are [B2B/B2C/hybrid] with [self-serve/sales-led] motion on [platform]. Aha Moment is [specific event], currently reached in [time]. Primary metric is [X], target is [Y]."

If you can't write this, you haven't discovered enough. Ask more questions before designing.
