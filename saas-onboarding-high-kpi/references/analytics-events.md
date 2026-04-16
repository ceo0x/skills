# Analytics Instrumentation

Without measurement, you're guessing at what's broken. Every onboarding component should emit events from day one — don't instrument after the fact.

## Critical Events (Must-Have)

```
onboarding_started
  - user_id, timestamp, signup_source, segment (if captured), device_type

onboarding_step_viewed
  - step_name, step_index, total_steps

onboarding_step_completed
  - step_name, step_index, time_on_step_seconds

onboarding_step_skipped
  - step_name, step_index

onboarding_step_error
  - step_name, step_index, error_code, error_category

onboarding_completed
  - total_time_seconds, steps_completed, steps_skipped

activation_achieved (Aha Moment)
  - time_from_signup_seconds, activation_action, segment

onboarding_dropped_off
  - last_step_name, last_step_index, session_duration_seconds
  - Fire on: tab close, 5-min idle, or navigation away

onboarding_resumed
  - time_since_drop_off_seconds, resume_step_name

checklist_item_completed
  - item_name, item_index, total_items, time_since_previous_item

checklist_completed
  - total_time_seconds, items_completed, items_skipped

help_requested
  - surface (tooltip | chat | doc_link), context_step, context_page
```

## Mobile-Specific Events

```
app_first_open
  - install_source (organic | paid | referral), platform (ios | android)

permission_prompt_shown
  - permission_type (push | location | camera | contacts | att), surface

permission_granted / permission_denied
  - permission_type, time_from_prompt_seconds

push_opt_in
  - trigger_context (post_value | post_async | pre_schedule)

deep_link_opened
  - campaign, source, target_screen

app_backgrounded_during_onboarding
  - step_name, session_duration_seconds

day_N_return
  - N (1 | 2 | 7 | 30), had_completed_onboarding
```

## Funnel Definitions

Events without a funnel are noise. Define these up front:

### Activation Funnel
```
signup
  ↓
onboarding_started
  ↓
step_1_completed → step_2_completed → ... → onboarding_completed
  ↓
activation_achieved
```

Track drop-off rate between each stage. The steepest drop is your next test target.

### Retention Correlation
```
Group users by: activated_in_first_session (yes/no)
Compare:
  - day_7_retention
  - day_30_retention
  - trial_conversion (if applicable)
```

Users who activate in their first session should show materially higher retention. If they don't, your activation definition may be wrong (see `aha-moments.md`).

### Segment Performance
```
Segment users by: [dimension from segmentation.md, e.g., job-to-be-done]
Compare across segments:
  - time_to_activation
  - onboarding_completion_rate
  - 30_day_retention
```

Use to decide whether segmentation is actually producing differentiated outcomes or just adding friction.

## Provider Detection

Use the project's existing analytics library if detected:
- Segment, PostHog, Mixpanel, Amplitude, Rudderstack, Heap, `gtag`, Plausible, Snowplow

If none detected, produce a thin `track(event, properties)` wrapper the user can plug into any provider. Do not lock them into a specific vendor by default.

Framework-agnostic wrapper concept:

```
track(eventName, properties)
  - merges in user_id, session_id, timestamp
  - batches for network efficiency
  - survives offline (queue + retry)
  - silent in dev unless explicit flag
```

## PII and Privacy

Treat analytics events as data you're responsible for.

- **Never include raw PII** in event properties — no names, emails, phone numbers, addresses
- **Hash user identifiers** if sent to third-party analytics
- **Respect Do Not Track** and GDPR/CCPA consent — suppress events for users who've opted out
- **Log the intent, not the content** — "user_submitted_form" yes; "user_submitted_form: {name: ..., ssn: ...}" no
- **Redact on ingestion** for any field that might contain user input (titles, descriptions, messages)
- **Document the schema** — every event in a shared doc, reviewed when new fields are added

Bad instrumentation is a compliance incident waiting to happen. Good instrumentation is invisible to the user and answers every product question.

## Sampling and Cost

- Sample-by-session (keep full event streams per sampled user) beats sample-per-event (loses funnels)
- In high-volume environments, sample 10-20% of users for full funnel; 100% for critical events (signup, activation)
- Never sample activation events — they're too rare and too important

## Event Naming Conventions

Pick one convention and stick with it:
- `snake_case_past_tense` — `onboarding_step_completed` (readable, sortable)
- `Noun Verbed` — `Onboarding Step Completed` (human-readable in dashboards)
- Prefix by domain — `onb_step_completed` (searchable in a busy schema)

Whichever you pick, document it and enforce it in code review. Mixed conventions create analytics chaos that compounds over years.
