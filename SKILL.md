---
name: vibe-2-product
description: Turn a long agent run or vibe-coded prototype into clear product decisions by auditing the existing codebase feature by feature and recording keep/refine/drop decisions in a persistent markdown log. Use when the codebase contains useful features, half-finished ideas, placeholders, and accidental complexity that need product refinement before more implementation.
---

# Vibe 2 Product

Use this skill for interactive product/codebase audits where the user wants to
understand every implemented feature and decide whether to keep, refine, or drop
it.

## Workflow

1. Create or locate a persistent markdown decision log early.
   - Prefer a repo-local file such as `docs/vibe-2-product-decisions.md`.
   - If the repo has a different docs convention, follow it.
   - Record decisions immediately after each keep/refine/drop answer.

2. Map the codebase before asking decisions.
   - Identify public commands, major modules, tests, docs, and feature groups.
   - Use `rg` / `rg --files` first.
   - Read implementation and tests before explaining a feature.

3. Walk one feature at a time.
   - Give a short, simple, accurate description.
   - Say where it is implemented.
   - Explain what works now, what is placeholder/toy/internal, and what inputs it needs.
   - Answer clarification questions before asking for a decision.
   - Ask for exactly one decision: keep, refine, or drop.

4. Record the decision.
   - Include the feature name, decision, and concrete refinement/removal notes.
   - Preserve the user's wording when it carries product intent.
   - Add open research/design tasks when needed.
   - Do this before moving to the next feature.

5. Continue until complete or stopped.
   - Do not skip features because they seem internal.
   - If a feature is only developer/test infrastructure, say so plainly.
   - If the user redirects, honor the newest request and then resume the loop.

## Explanation Style

- Use simple but precise language.
- Separate current implementation from recommended refinement.
- Distinguish user-facing features from developer infrastructure.
- Flag toy/prototype behavior explicitly.
- Avoid treating a code path as production-ready just because tests exist.
- When the user asks for clarification, pause the decision loop and clarify first.

## Decision Log Shape

Use concise entries like:

```markdown
### N. Feature Name

Decision: keep and refine.

Notes:
- What it does now.
- What the user decided.
- Required refinements, removals, or research tasks.
```

Maintain an `Open Research / Design Tasks` section when the walkthrough creates
follow-up work that should not be lost.

## Guardrails

- Never rely only on conversation memory for decisions.
- Never continue to the next feature before recording the current decision.
- Do not implement broad refactors during the walkthrough unless the user asks.
- If asked to implement later, use the decision log as the source of truth.
- Protect unrelated user changes in the repo.
