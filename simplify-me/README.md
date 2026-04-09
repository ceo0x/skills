# simplify-me

A Claude Code skill that relentlessly simplifies your code, concepts, and decisions — one question at a time.

## What it does

Challenges every piece of code, concept, or decision with a single question: **"Is this strictly necessary?"**

Instead of just asking, it proposes the simpler version itself — so the conversation moves fast and you end up with leaner code.

## Install

```
npx skills@latest add ceo0x/skills/simplify-me
```

## Usage

Run `/simplify-me` inside Claude Code, then paste or reference the code/concept/decision you want to simplify.

## Example

> **You:** `/simplify-me` — here's my API client setup [...]
>
> **Claude:** This `retry` wrapper duplicates what `axios` already does with `axios-retry`. Is it strictly necessary? Simpler version: remove it and add `axios-retry` with `{ retries: 3 }`.
