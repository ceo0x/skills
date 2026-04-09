# why-not

A Claude Code skill that challenges every decision in your design or code by proposing concrete alternatives — one at a time, with pros/cons and a clear recommendation.

## What it does

For each decision it finds, it asks: **"Why not do it this other way instead?"**

It doesn't just raise doubts — it presents a real alternative, weighs the trade-offs, and tells you what it would actually recommend.

## Install

```
npx skills@latest add ceo0x/skills/why-not
```

## Usage

Run `/why-not` inside Claude Code, then paste or reference the design or code you want challenged.

## Example

> **You:** `/why-not` — we're using REST for this internal service [...]
>
> **Claude:** Why not use tRPC instead? **Pros:** end-to-end type safety, no schema drift, less boilerplate. **Cons:** couples client and server to TypeScript, harder to call from non-TS clients. **Recommendation:** use tRPC if both sides are TypeScript — the type safety alone pays for the coupling.
