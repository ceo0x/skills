# name-guard

A skill that audits naming across your codebase — one bad name at a time — and proposes a better one with a clear reason before moving on.

## What it does

Finds naming inconsistencies, ambiguous identifiers, and misleading names. For each one it proposes a concrete replacement and explains exactly why it makes the code clearer. Waits for your approval before moving to the next — so every rename is intentional.

## Install

```
npx skills@latest add ceo0x/skills/name-guard
```

## Usage

Run `/name-guard` inside your agent, then point it at the codebase or file you want audited.

## Example

> **You:** `/name-guard`
>
> **Claude:** **Bad name — `data` in `processData(data)`**
> `data` tells you nothing about what's being passed. Every variable is "data".
> Better name: `orderPayload` — it signals the shape and intent, making the function self-documenting.
> Approve to continue to the next?
