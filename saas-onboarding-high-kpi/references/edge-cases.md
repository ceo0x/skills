# When the Rules Bend

The standard playbook (fast TTFV, self-serve, measurable Aha Moment) assumes a lot: that the user controls their own account, that value can be delivered in minutes, that the product is single-tenant, that the connection is reliable. When those assumptions break, the principles still hold but the tactics change.

## Unavoidably Long TTFV

Some products cannot deliver the Aha Moment fast:
- **K-12 ed-tech** — waits on district provisioning, roster sync, IT approval
- **Healthcare / HIPAA** — identity verification, BAA signing, credentialing
- **Compliance / GRC** — depends on scanning or audit cycles measured in days
- **Data pipelines** — first meaningful insight requires days of data accumulation
- **Recruiting / ATS** — Aha Moment is "first hire made" which can be weeks
- **Construction / industrial SaaS** — Aha Moment depends on field activity

### Adaptation

Split the Aha Moment into two:
1. **Proxy Aha** (in the first session) — a small validated step ("Your first scan is queued and will complete in 24 hours. Here's what you'll see when it does.")
2. **True Aha** (later) — the real retention-driving moment

Show the proxy Aha with a preview of the future state (screenshot, demo data, "this is what it'll look like"). Send re-engagement communications timed to the actual completion. Don't fake completion — users resent it.

Instrument both. Use the proxy as a leading indicator; optimize for the true Aha as the lagging one.

## Self-Serve → Sales-Led Hybrid (PQL to SQL)

Many B2B products start self-serve and route to sales based on behavior. The onboarding challenge: two conflicting goals.
- Self-serve wants friction minimized
- Sales needs qualifying information (company size, budget, timeline)

### Adaptation

Don't gate value behind qualification. Instead:
- Let the user self-serve to a meaningful point
- Detect PQL signals: usage velocity, team size invites, enterprise email domain, feature touches
- Trigger sales assist *in-app* when signals fire — not as a gate, as an offer ("Want help setting this up? We do live walkthroughs.")
- Keep the self-serve path open even for PQLs — some enterprises buy without ever talking to sales

Wrong: forcing "Talk to sales" at signup.
Right: self-serve works end to end; sales surfaces as helpful option when the user looks like ICP.

## Multi-Tenant White-Label

Platforms where your customer's customers onboard: payment processors, communication APIs, embedded fintech, developer platforms.

### Adaptation

- You onboard the platform customer (normal SaaS onboarding)
- The platform customer onboards their end-users — your job is to give them the *tools* to do it well (configurable flows, branded templates, event hooks)
- Don't dictate their UX; provide primitives
- Document the patterns from this skill as best practices in your SDK

Key: don't conflate the two onboarding layers. Your metrics (platform activation) are distinct from theirs (end-user activation).

## Offline-First Apps

Note-taking, field services, logistics, certain mobile apps.

### Adaptation

- First-run must work offline up to the point of auth
- Sync analytics when connection resumes; don't drop events
- Handle signup race conditions: user might sign up on device A while device B is offline and queue conflicting changes
- State persistence is non-negotiable, not a nice-to-have
- Show connection state explicitly — "Saved locally, will sync when online"
- Test onboarding on airplane mode before shipping

## Regulated Signups (Healthcare, Finance, Legal)

KYC, HIPAA, age verification, GDPR consent — all have legal requirements that add steps.

### Adaptation

- You can't remove these steps; you can reorder them
- Put legal consent at minimum-friction moments (not cold on signup)
- Explain *why* each data request is needed ("We ask for your date of birth because [regulation X] requires it to offer this service")
- Split compliance into "must have before use" vs "must have before export/production"
- Social proof and reassurance become more important (users are warier with regulated products)
- Document compliance decisions — auditors will ask, and "we decided this for UX" is not a defense

## B2B2C / Platforms

Your users aren't the end-users — they're builders, resellers, or operators serving their own customers.

### Adaptation

- Onboarding is about *enabling* them to onboard their customers
- Templates and white-label flows matter more than finished UX
- Measure their activation (build first integration, configure first tenant) differently from their customers'
- Examples: Shopify store owners vs shoppers; Slack admins vs end users; Stripe merchants vs cardholders

## Very Long Sales Cycles (Enterprise Annual Contracts)

The "trial" is a pilot that may run for months, with procurement, security review, and legal in parallel.

### Adaptation

- TTFV measures shift — "first value for the evaluator" matters, not just the end-user
- Onboarding is multi-persona: admin/IT, end-user, executive sponsor
- Provide admin-facing dashboards showing adoption (helps them justify purchase internally)
- Instrument for the whole buying committee, not just the active user
- Concierge touchpoints become primary channel, not exception

## Very High Frequency / Habit Products

Apps opened multiple times daily (social, messaging, fitness, games).

### Adaptation

- The "Aha Moment" is less important than the "habit loop" — trigger, action, reward
- Optimize for day-2, day-3, day-7 return rates, not flow completion
- Notification opt-in is load-bearing — without it, users don't form habits
- Push content that rewards return visits (personalized, time-relevant)

## When to Break Rules vs Bend Them

**Bend** (common): slower TTFV, more steps, more verification — if the domain genuinely requires it. Keep the principles (fast time-to-perceived-value, Zeigarnik open loops, progress visibility).

**Break** (rare): any time you're tempted, audit first. Usually the user isn't actually in an edge case; they've just internalized legacy constraints that could be engineered away. The list above is the real set of edge cases — most other "our case is different" claims aren't.
