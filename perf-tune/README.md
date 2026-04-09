# perf-tune

A skill that analyzes your code for performance issues one bottleneck at a time — with a clear explanation of the impact and the exact optimized code ready to apply.

## What it does

Identifies the most significant bottleneck or hot path in your code, explains why it matters (latency, memory, CPU, I/O), and proposes the exact fix. It waits for your approval before moving on to the next one — so you stay in control of every change.

## Install

```
npx skills@latest add ceo0x/skills/perf-tune
```

## Usage

Run `/perf-tune` inside your agent, then paste or reference the code you want to optimize.

## Example

> **You:** `/perf-tune` — here's our data processing pipeline [...]
>
> **Claude:** **Bottleneck #1 — repeated `.find()` inside a loop (O(n²))**
> Every iteration scans the full array to match an ID. On 10k items this is ~100M comparisons.
> Optimized version: build a `Map` once before the loop and do O(1) lookups.
> `[exact code shown]`
> Approve to continue to bottleneck #2?
