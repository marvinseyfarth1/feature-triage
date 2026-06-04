# Codebase Feature Walkthrough

A Codex skill for turning an unclear existing codebase into explicit product
decisions.

It walks through a repository feature by feature, explains what is actually
implemented, asks for one decision at a time, and records each decision in a
markdown log.

## Why

AI-assisted builds can produce a lot of code quickly. After a long-running agent
goal, a vibe-coded prototype, or an inherited codebase, it is often unclear what
should be kept, refined, or removed.

This skill creates a structured refinement pass before implementation work
continues.

## What It Does

- Maps the codebase before asking for decisions.
- Explains one feature at a time in plain technical language.
- Distinguishes real behavior from placeholder, toy, or internal code.
- Asks for exactly one decision per feature: keep, refine, or drop.
- Records every decision in a persistent markdown log.
- Uses the decision log as the source of truth for later implementation.

## Good Use Cases

- Refining a vibe-coded prototype.
- Reviewing a codebase produced by a long-running Codex goal.
- Understanding an inherited project before cleanup.
- Turning scattered generated features into a product roadmap.
- Separating useful functionality from accidental complexity.

## Install

Clone this repository into a Codex skill location:

```bash
git clone https://github.com/marvinseyfarth1/codebase-feature-walkthrough.git ~/.agents/skills/codebase-feature-walkthrough
```

If your Codex setup uses `~/.codex/skills` for personal skills, clone it there
instead:

```bash
git clone https://github.com/marvinseyfarth1/codebase-feature-walkthrough.git ~/.codex/skills/codebase-feature-walkthrough
```

Restart Codex if the skill does not appear immediately.

## Usage

Invoke it explicitly:

```text
Use $codebase-feature-walkthrough to walk me through this codebase feature by feature.
Explain each feature, ask whether to keep, refine, or drop it, and record every decision in a markdown log.
```

For a repo-local team skill, copy or vendor this folder under:

```text
.agents/skills/codebase-feature-walkthrough/
```

## Decision Log

The skill prefers a repo-local file such as:

```text
docs/feature-walkthrough-decisions.md
```

See [examples/feature-walkthrough-decisions.md](examples/feature-walkthrough-decisions.md)
for the expected shape.

## LinkedIn Blurb

```text
I built a small Codex skill for a problem I keep running into:

After a long agent run, or after vibe coding a prototype, the codebase often contains a mix of useful features, half-finished ideas, placeholders, and accidental complexity.

This skill walks through the codebase feature by feature, explains what is actually implemented, asks whether to keep/refine/drop each feature, and records every decision in a markdown log.

The goal is simple: turn an unclear generated codebase into an actionable refinement plan.
```

## License

MIT
