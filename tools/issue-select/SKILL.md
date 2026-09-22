---
name: issue-select
description: Grade a candidate open-source issue against a written rubric and decide whether it is worth taking as a first contribution. Use when evaluating a GitHub issue URL or an eval snapshot file as a potential first issue.
---

# issue-select: rubric-driven first-issue grading

You are grading one candidate issue to answer a single question: should a
newcomer take this as their first contribution to this repo? You do not
answer from gut feel. You answer by executing the rubric in `rubric.md`,
check by check, against evidence you gather.

## Inputs

One of:

- **Live mode**: one or more GitHub issue URLs. Gather evidence from the live
  repo with `gh`, the GitHub API, or the web. The evidence guide says where
  each signal lives.
- **Eval mode**: a snapshot bundle containing the issue text, comment thread,
  and repo facts. Use only the bundle text as evidence.

## Scope and rubric

In live mode, read `scope.md` first. Confirm that the candidate is in the
scoped source, apply its house rules, and use its fit profile only to rank
issues that the rubric accepts. In eval mode, ignore `scope.md`.

Read `rubric.md`, then execute every check in its table. Each check must be
graded `pass`, `fail`, or `unclear` with a one-line quote or fact that decided
it. Apply the verdict rule exactly. Preferred checks can rank accepted issues
but never change a verdict.

## Output

For each issue, show a short readable summary, then end with a fenced JSON
block and no text after it:

```json
{
  "item": "<issue URL or bundle id>",
  "checks": [
    {"name": "<check name>", "grade": "pass|fail|unclear",
     "evidence": "<one line: the fact or quote that decided it>"}
  ],
  "verdict": "accept|reject"
}
```

For multiple live candidates, list accepted issues first in fit order, followed
by rejected issues. The final JSON block must contain an array of their
per-issue objects in that order.

## Grading discipline

- Name the deciding evidence for every grade.
- Grade the written rule, not an unstated intuition.
- Treat genuinely missing evidence as `unclear`; the verdict rule determines
  how it affects the result.
