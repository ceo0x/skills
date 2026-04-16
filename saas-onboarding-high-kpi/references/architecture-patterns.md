# Architecture Patterns

Pick exactly one primary pattern. Mixing patterns produces confused flows. You can layer techniques (checklist on top of wizard) but the primary architecture is singular.

## Decision Tree

Start here:

1. Is the user a developer integrating via API/CLI? → **API-First**
2. Is the primary platform a mobile app? → **Mobile-Native** (see `mobile-native.md`)
3. Does value require teammates to be present? → **Team-First**
4. Is the Aha Moment a premium-tier feature? → **Reverse Trial**
5. Does the product have a steep learning curve with empty-state paralysis? → **Sandbox / Template**
6. Does the product need seed data or real configuration before value appears? → **Guided Wizard**
7. None of the above — value is immediate once configured? → **Lightning Setup**

## Pattern 1: Lightning Setup

**When:** Product value is immediate once configured. No team dependency. Examples: monitoring tools, simple analytics, password managers.

```
Signup → OAuth / Connect (1 click) → Auto-configure → Aha Moment → Checklist for depth
```

**Target:** TTFV < 3 minutes. **Key principle:** Minimize steps. Zero configuration is better than one step.

## Pattern 2: Guided Wizard

**When:** Product needs seed data or meaningful configuration before value appears. Examples: CRM, project management, marketing automation.

```
Signup → Segment question (1 screen) → Wizard (3-5 steps) → Aha Moment → Post-activation guidance
```

**Target:** TTFV < 10 minutes. **Key principle:** Value-first ordering. If a step is optional for the Aha Moment, defer it to the post-setup checklist.

## Pattern 3: Team-First

**When:** Product value depends on teammates. Examples: Slack, Figma, Notion, shared calendars.

```
Signup → Workspace creation → Invite teammates (with skip) → First collaborative action → Aha Moment
```

**Target:** TTFV < 30 minutes (includes teammate join time). **Key principle:** Show solo value first, then amplify with team. Never block activation on an external dependency.

## Pattern 4: Reverse Trial

**When:** Aha Moment involves a premium feature. Free tier alone doesn't showcase full value. Examples: Grammarly Premium, Canva Pro, Zoom Pro.

```
Signup → Full premium access (14 days) → Guided to premium Aha Moment → Usage-based nudge → Graceful downgrade
```

**Target:** Trial-to-paid > 25%. **Key principle:** Let users taste premium before asking to pay. Downgrade gracefully — preserve content, disable only premium features.

## Pattern 5: Sandbox / Template

**When:** Product has steep learning curve. Blank-slate paralysis is the biggest drop-off. Examples: Webflow, Airtable, Retool, Notion workspaces.

```
Signup → "Start from template" or "Explore demo" → Edit template (low risk) → Aha Moment → Create own project
```

**Target:** TTFV < 5 minutes in sandbox. **Key principle:** Remove blank-slate risk. Editing a template is psychologically easier than creating from scratch.

## Pattern 6: API-First / Developer

**When:** Primary users are developers integrating via API or CLI. Examples: Stripe, Twilio, SendGrid, Supabase.

```
Signup → API key generated instantly → Copy-paste quickstart (curl/SDK) → First successful call → Dashboard shows result
```

**Target:** First successful API call < 5 minutes. **Key principle:** Developers want to copy-paste and see a response. Every screen between signup and the first working request is waste.

## Pattern 7: Mobile-Native

**When:** Primary platform is an iOS or Android app. Mobile has constraints web patterns miss: app review, OS permission prompts, push opt-in as a one-shot conversation, 70-second average sessions.

See `mobile-native.md` for the full flow and mobile-specific rules (permission timing, deferred sign-in, deep link handling, first-run behavior).

## Layering Techniques

You can add these on top of any primary pattern:
- **Checklist** — post-setup activation (pairs with Lightning, Wizard, Team-First)
- **Templates** — reduce blank-slate risk (pairs with Wizard)
- **Reverse trial copy** — trial expiration emails even if not a true reverse trial
- **Segmentation question** — 1 question that branches the flow (pairs with Wizard, Sandbox)

Don't layer more than 2 techniques on one pattern. Complexity compounds.
