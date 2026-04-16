# Segmentation Framework

Personalize onboarding along 1-2 dimensions, never more. Every question before value delivery costs roughly 10-15% completion — segmentation has to earn its place.

## Dimensions

| Dimension | How to Capture | How It Changes the Flow |
|---|---|---|
| **Job-to-be-Done** | Post-signup question: "What's your main goal?" (3-4 options) | Different checklist items, different Aha Moment path |
| **Role** | Post-signup question or domain inference | Admin → setup/config path; end-user → usage path |
| **Company Size** | Post-signup question or enrichment (Clearbit, etc.) | Solo → skip team invite; Enterprise → emphasize SSO |
| **Technical Sophistication** | Infer from signup source or ask | Technical → API quickstart; Non-technical → GUI wizard |
| **Traffic Source / Intent** | UTM params, referral source | "From competitor comparison" → migration wizard; "From blog about X" → X-focused flow |
| **Platform** | Detect on signup | Mobile-first vs desktop-first flow choice |

## Selection Rules

1. **Pick only 1-2 dimensions.** All six dimensions produce combinatorial branching no small team can maintain, instrument, or test.
2. **Prefer inference over asking.** UTM source, email domain, signup device — infer what you can. Only ask what you can't detect.
3. **Ask at most 1 question before value.** If the segmentation only produces minor branching, skip the question and serve one good flow.
4. **Capture segmentation data in analytics regardless.** Segment the funnel even if you don't branch the flow now. Data now enables branching later.

## Good vs Bad Segmentation Questions

**Good:**
- "What's your main goal with [Product]?" (3-4 concrete options, each mapping to a distinct flow)
- "Are you setting this up for yourself or a team?" (2 options, meaningful branch)

**Bad:**
- "Tell us about yourself" (open-ended, no branch)
- "Select all that apply" (multi-select kills single-decision clarity)
- "What's your industry?" (too many options, usually no meaningful branch)
- 3+ questions on 3+ screens before any value

## Progressive Profiling

Capture what you need *later* when it's useful, not upfront. Examples:
- Ask for company name when they invite their first teammate, not at signup
- Ask for phone number when they configure SMS alerts, not on day 1
- Ask for use case detail when they're building their first project, not before

Every field you defer is a percentage point of completion back.

## When to Skip Segmentation Entirely

If your product has:
- One clear primary use case
- Low traffic volume (< 500 signups/week, not enough to statistically validate branches)
- Early stage (< 10,000 total users) where branching creates maintenance burden

Then skip the segmentation question. Build the best single flow you can. Add segmentation later when you have volume and clear divergent needs.

Segmentation is a tool for scaling nuance, not a starting point.
