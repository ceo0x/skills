# Mobile-Native Onboarding

Mobile has constraints web doesn't: app review policies, OS permission prompts that can't be A/B tested freely, push notification opt-in is a one-shot conversation, and attention windows are shorter (average mobile session is around 70 seconds vs web's 3-5 minutes).

## The Mobile Flow

```
App install → App open → Value preview (2-3 screens max) → Deferred sign-in OR sign-in → First core action → Permission prompts (after value) → Push opt-in (contextual) → Aha Moment → Home
```

**Target:** First core action < 60 seconds from first open. Aha Moment < 2 minutes.

## Mobile-Specific Rules

### 1. Defer sign-in when possible
Let users experience the core value before asking for an account. Apple's App Store guidelines actively favor "guest mode" or "try before you sign up." Deferred sign-in typically raises day-1 retention 15-40%.

Exceptions: social products (need identity), financial (need KYC), health (need profile).

### 2. Permission prompts come after value, never before
- **Notifications** — ask after user completes their first meaningful action, with context explaining why
- **Location** — ask when the feature needing it is first used
- **Camera / Photos** — same
- **Contacts** — only if the feature is core; otherwise skip

iOS in particular only lets you ask each permission once (for push). If users decline, they must go into Settings to reverse — so the first ask has to land. Pre-prompt with a custom screen ("We send notifications when your report is ready — enable them?") before the OS prompt fires. This two-step approach roughly doubles opt-in rates because declining the soft prompt doesn't burn the hard prompt.

### 3. Push opt-in timing
Best moments to ask:
- After first value delivered (user has context for why notifications help)
- After a long-running async action starts (user needs to be notified when it finishes)
- Before the user would naturally check back (scheduled report, bid update, etc.)

Worst moments:
- On first open (no context, declines guaranteed)
- During signup (feels like a demand)
- Immediately after declining another permission (fatigue)

### 4. App Tracking Transparency (iOS)
If you use IDFA or third-party analytics, the ATT prompt is mandatory. Same rule: pre-prompt with context, show after first value, not on launch. Acceptance rates for contextual pre-prompts run 40-60% vs 20-30% for cold ATT.

### 5. Deep links from marketing
Users arriving from marketing campaigns land on specific features — don't force them through generic onboarding. Install attribution (Branch, AppsFlyer, Adjust) should route users into deep-link-specific flows that show value for *that* campaign.

### 6. Gesture-based patterns
Mobile users expect:
- Swipe between onboarding screens (3-5 screens max, carousel pattern)
- Pull-to-refresh for data-driven apps
- Long-press affordances for power features (discoverable later, not in onboarding)

### 7. First-run coach marks
Max 2-3 coach marks, dismissible, with "Don't show again." Longer sequences have 90%+ skip rates on mobile. Prefer contextual tips triggered by behavior (e.g., "Try swiping left on an item" when the user hovers on a list).

### 8. Offline-capable first run
Users may open the app on a plane, subway, or flaky connection. First-run should work offline up to the point of sign-in or data sync. Show cached onboarding content, queue analytics events, retry sign-in gracefully.

### 9. Mobile completion = install retention
On mobile, the meaningful "onboarding complete" metric is often **day-2 or day-3 retention**, not a flow-complete event. A user who finishes the wizard and never returns didn't really onboard. Design and measure for the return visit.

### 10. Cold-start re-engagement
If a user opens the app on day 3 having not returned, show them where they left off — don't restart the flow. A day-3 returner is higher-intent than a day-0 installer and deserves a different experience (resume, not repeat).

## Mobile Copy Differences

- **Shorter headlines** — 4-6 words max on small screens
- **Benefit-first buttons** — "See my dashboard" beats "Continue"
- **Thumb-zone CTAs** — primary buttons on the bottom third of the screen
- **Skip options visible** — Apple reviewers sometimes reject flows without a clear skip; users with app fatigue churn without one
- **Locale-aware** — mobile apps reach global audiences fast; plan for translation from day one

## Mobile Analytics Notes

Key events specific to mobile (full list in `analytics-events.md`):
- `app_first_open` — different from signup; captures pre-account behavior
- `permission_prompt_shown` / `permission_granted` / `permission_denied` — per permission type
- `push_opt_in` — separate from other notification events, since this is usually a one-shot
- `deep_link_opened` — with campaign / source attribution
- `app_backgrounded_during_onboarding` — drop-off proxy for mobile
- `day_N_return` — primary success metric, N ∈ {1, 2, 7, 30}

## Anti-Patterns on Mobile

- Forcing signup before the user sees anything
- Asking for all permissions on launch
- Long text-heavy intro carousels (users swipe past)
- Modal interstitials that block the home screen
- Requiring email verification before any app use
- Gating the app behind a tutorial the user can't skip
- Ignoring dark mode and dynamic type preferences
- Blocking the app during onboarding update downloads

## Platform-Specific Considerations

### iOS
- App Store Review Guidelines reject forced-account flows for apps that could work anonymously
- ATT prompt has strict wording rules — don't promise anything the OS prompt contradicts
- Universal Links > custom URL schemes for deep links
- Support Sign in with Apple if offering other third-party sign-ins

### Android
- Google Play policy is more permissive on sign-in, stricter on permissions post-API 30
- Use Android's deep link intent filters and App Links (digital asset links) for domain verification
- Adaptive icons, dynamic colors (Material You) — if supported, honoring these earns trust
- Handle back-button navigation throughout onboarding (users will hit back; don't lose state)
