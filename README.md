# Feature Triage

An agent skill for turning an unclear existing codebase into explicit product
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
- Reviewing a codebase produced by a long-running coding-agent goal.
- Understanding an inherited project before cleanup.
- Turning scattered generated features into a product roadmap.
- Separating useful functionality from accidental complexity.

## Compatibility

This is a plain `SKILL.md` skill following the common Agent Skills shape:

```text
feature-triage/
└── SKILL.md
```

It should work with coding agents that support filesystem skills based on
`SKILL.md`, including Claude Code and Codex. The workflow itself is not tied to
any one agent.

The main differences are where each agent expects skills to live and how you
invoke them.

## Install

Clone this repository into a skill location for your agent.

Claude Code personal skill:

```bash
git clone https://github.com/marvinseyfarth1/feature-triage.git ~/.claude/skills/feature-triage
```

Claude Code project skill:

```bash
git clone https://github.com/marvinseyfarth1/feature-triage.git .claude/skills/feature-triage
```

Codex personal skill:

```bash
git clone https://github.com/marvinseyfarth1/feature-triage.git ~/.agents/skills/feature-triage
```

Codex project skill:

```bash
git clone https://github.com/marvinseyfarth1/feature-triage.git .agents/skills/feature-triage
```

Restart your agent if the skill does not appear immediately.

## Usage

Ask your agent to use Feature Triage:

```text
Use Feature Triage to walk me through this codebase feature by feature.
Explain each feature, ask whether to keep, refine, or drop it, and record every decision in a markdown log.
```

If your agent supports explicit skill invocation, use the installed skill name:

```text
feature-triage
```

## Decision Log

The skill prefers a repo-local file such as:

```text
docs/feature-triage-decisions.md
```

See [examples/feature-triage-decisions.md](examples/feature-triage-decisions.md)
for the expected shape.

## LinkedIn Blurb

```text
I built a small agent skill for a problem I keep running into:

After a long coding-agent run, or after vibe coding a prototype, the codebase often contains a mix of useful features, half-finished ideas, placeholders, and accidental complexity.

This skill walks through the codebase feature by feature, explains what is actually implemented, asks whether to keep/refine/drop each feature, and records every decision in a markdown log.

The goal is simple: turn an unclear generated codebase into an actionable refinement plan.
```

## License

MIT
