# Multi-Channel Orchestration

In-app is only one channel. World-class onboarding coordinates in-app, email, and human touchpoints — each doing what the others can't.

## Channel Responsibilities

### In-App (Primary)
- Stepper wizard for initial setup
- Persistent checklist for post-setup actions
- Contextual tooltips triggered by user behavior (not time)
- Empty states that guide to first action
- Celebration moments at Aha Moment and checklist completion
- In-app re-engagement nudges (bottom bar, banner)

### Email (Support Channel)
Trigger-based, not time-based. Each email has a specific behavioral trigger and a single clear CTA.

| Trigger | Email | Goal |
|---|---|---|
| Signup + 1 hour, no Aha Moment | "Quick start: 3 steps to [value]" | Bring back to complete setup |
| Aha Moment reached | "You did it! Here's what to try next" | Reinforce and deepen |
| Day 3, < 50% checklist | "You're almost there — [next step] takes 2 min" | Re-engage with specific CTA |
| Day 7, no return visit | "Here's what you're missing" (value shown from similar users) | FOMO-driven re-engagement |
| Day 12 (if trial), active | "Your trial ends in 2 days — here's what you'll keep/lose" | Convert with loss aversion |
| Invited teammate joins | "Welcome! [Inviter] set things up — here's your quick start" | Secondary user activation |

### Human Touchpoints (High-Value Accounts)
- **Automated but personal** — Founder/CS email at day 1 ("Reply if you need anything"). Make it look like a real person — because it is, and it should genuinely accept replies.
- **Usage-triggered** — If account matches ICP AND shows high engagement, route to sales-assist. The combination matters — ICP alone isn't enough; engagement without ICP means they're not a revenue prospect.
- **Concierge onboarding** — For enterprise, offer a live setup call *after* self-serve attempt, not before. Pre-served live help is demotivating; post-attempt live help is welcomed.

## Lifecycle Stages

Onboarding is not a one-time event. Different channels fit different stages:

| Stage | Duration | Primary Channel | Example Actions |
|---|---|---|---|
| Signup → Setup | Minutes | In-app | Account, connection, first config |
| Setup → Aha Moment | Minutes to hours | In-app + email re-engagement | Guided to first value |
| Aha Moment → Habit | Days 1-14 | In-app checklist + trigger email | Repeated use, feature exploration |
| Habit → Expansion | Weeks 2-8 | Email + human | Team invites, integrations, advanced features |
| Expansion → Advocacy | Months 2+ | Human + community | Templates, referrals, participation |

Don't dump stage 3-5 content on a day-1 user. Don't send advanced-feature emails to users who haven't hit the Aha Moment yet.

## Channel Coordination Principles

1. **One primary CTA per moment.** If in-app is asking for action A, don't send an email asking for action B at the same time — conflicting CTAs halve completion.
2. **Suppress email when user is active in-app.** If the user is currently using the product, the "come back" email is annoying. Implement active-session suppression (e.g., don't send re-engagement if user was active in the last 30 min).
3. **De-dupe across channels.** If the user completes the CTA in-app, the email about that CTA should cancel.
4. **Human touchpoints escalate, they don't repeat.** If a user has talked to a CSM, don't keep sending them automated "need help?" emails.
5. **Channel should match stakes.** A failed integration merits an email. A skipped tutorial doesn't.
6. **Frequency caps.** No more than 1 onboarding email per 24 hours. No more than 3 per week. More than that, users mark as spam regardless of content.
