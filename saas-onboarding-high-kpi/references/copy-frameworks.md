# Copy Frameworks

## The Onboarding Copy Formula

Every piece of onboarding copy follows: **Outcome → Action → Effort**

- Bad: "Click here to configure your workspace settings"
- Good: "Start collaborating — set up your workspace in 30 seconds"

Outcome tells users why to act. Action tells them what. Effort tells them the cost. All three reduce friction.

## Microcopy Principles

1. **Lead with the benefit**, not the action: "See your data in real time" > "Connect your database"
2. **Include time estimates**: "Takes about 2 minutes" reduces anxiety and increases starts
3. **Second person + active voice**: "You'll see your first report" > "A report will be generated"
4. **Celebrate with specificity**: "You just analyzed 12,847 rows in 3 seconds" > "Great job!"
5. **Make skip options guilt-free**: "Skip for now — you can do this anytime" > "Skip"
6. **Social proof in context**: "Used by 3,200 teams this week" at the moment of commitment
7. **Concrete over vague**: "Your first dashboard" > "Your project"
8. **Avoid product jargon**: Users don't know your internal terminology — use their language

## Progress Copy

Match copy to where the user is in the flow:

| Position | Copy Style | Example |
|---|---|---|
| Start | Set expectation | "Let's get you to your first [value] — 4 quick steps" |
| Mid | Maintain momentum | "Halfway there! [Next step] is the fun part" |
| Near-end | Leverage goal gradient | "One more step and you're all set" |
| Complete | Celebrate specifically | "You're live! [Specific achievement]. Here's what to explore next" |

## Reusable Templates

### Welcome Screen
```
Welcome to [Product]!
Let's get you to your first [specific value] in under [time].
[Primary CTA: "Get Started — takes 2 minutes"]
[Secondary: "Explore a demo first"]
```

### Segmentation Question
```
What's your main goal with [Product]?
- [Goal A — e.g., "Track my team's performance"]
- [Goal B — e.g., "Automate my reporting"]
- [Goal C — e.g., "Monitor my infrastructure"]
- Something else
```

### Onboarding Checklist
```
Your setup checklist (3 of 5 complete)
[x] Create your account
[x] Connect [integration]
[x] [First core action — completed!]
[ ] Invite a teammate (~1 min)
[ ] Set up your first [advanced feature] (~3 min)
```

### Empty State
```
[Illustration of populated state]
Your [items] will appear here
[Benefit of having items] — get started in under a minute.
[Primary CTA: "Create your first [item]"]
[Secondary: "Import from [source]" | "Use a template"]
```

### Celebration
```
You did it!
You just [specific achievement with data — e.g., "analyzed 12,847 rows in 3 seconds"].
You're faster than 80% of new users.
[Primary CTA: "Explore what's next"]
[Secondary: "Share your setup"]
```

### Re-engagement Email (Day 3)
```
Subject: You're 1 step away from [value]

Hi [Name],

You've already [completed step] — nice work.

The next step takes about 2 minutes: [specific action with direct link].

Teams who complete this step see [specific benefit with data].

[CTA: "Complete your setup"]

— [Founder name], [Product]

P.S. Hit reply if you're stuck — I read every email.
```

### Trial Expiration (Day 12, Active User)
```
Subject: Your trial ends in 2 days — here's what you'll keep

Hi [Name],

You've [specific usage stat, e.g., "created 12 projects and shipped 3"] on [Product]. Nice.

In 2 days, your trial ends. Here's what changes:

What you'll keep (free forever):
- [Feature 1]
- [Feature 2]

What you'll lose:
- [Premium feature you've been using]
- [Premium feature you've been using]

[Primary CTA: "Upgrade to keep everything"]
[Secondary: "Downgrade to free"]

— The [Product] team
```

### Invited Teammate Welcome
```
Welcome to [Workspace name]!

[Inviter name] set everything up — you're ready to jump in.

Here's what they've built so far:
- [Specific thing 1]
- [Specific thing 2]

[Primary CTA: "See the workspace"]

Want a quick tour? [Secondary CTA: "Show me around (~1 min)"]
```

## Copy Anti-Patterns

- **Faux enthusiasm** — "Awesome! You're amazing!" without specifics feels hollow
- **Cryptic errors** — "Something went wrong" tells the user nothing actionable
- **Threatening urgency** — "LAST CHANCE!!!" erodes trust; use loss aversion honestly
- **Generic praise** — "You did it!" without what-you-did is noise
- **Jargon** — "Your org's RBAC config is syncing" loses non-technical users
- **Pretending to be personal when it isn't** — "Hey friend!" from a no-reply address is worse than no personalization
- **Walls of text** — users don't read. 3+ lines per screen is 2 too many.

## Localization Notes

If the product serves multiple markets, design copy for translation from day one:
- Avoid idioms and cultural references that don't translate
- Budget 20-30% extra space for German/Finnish/Russian, which run longer
- Don't concatenate strings programmatically — different languages order words differently
- Dates, numbers, currency, and honorifics all need locale-aware rendering
