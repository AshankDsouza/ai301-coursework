# Unit 1 — Issue Selection

## Selected issue

**Issue link**

https://github.com/codepath/pathreview-ai301-fa26-s1/issues/73

**Verdict output**

issue-select: `README and .env.example disagree about which LLM API key to set`

- `maintainer-active`: pass — three human-authored commits landed on
  2026-09-16, within the rubric's 90-day window.
- `repo-in-use`: pass — the repository is not archived and was pushed on
  2026-09-16, within the 180-day window.
- `newcomer-bounded`: pass — the issue names the two affected files
  (`README.md` and `.env.example`) and asks them to agree with
  `core/config.py`; it is one documentation/configuration correction.
- `available`: pass — GitHub reports no assignee, no comments, and no linked
  pull requests. The Path Review house rule would also allow a shared issue.
- `ai-policy-compatible`: pass — `docs/CONTRIBUTING.md` specifies testing and
  pull-request requirements but has no AI-assistance ban.
- `starter-signals`: pass — the issue is labeled both `good first issue` and
  `tier-1`, and it names the expected configuration behavior.

```json
{
  "item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/73",
  "checks": [
    {
      "name": "maintainer-active",
      "grade": "pass",
      "evidence": "The three newest main-branch commits are human-authored by Aburke225 on 2026-09-16."
    },
    {
      "name": "repo-in-use",
      "grade": "pass",
      "evidence": "The repository is not archived and its most recent push was 2026-09-16."
    },
    {
      "name": "newcomer-bounded",
      "grade": "pass",
      "evidence": "The issue identifies README.md and .env.example and asks that both match core/config.py."
    },
    {
      "name": "available",
      "grade": "pass",
      "evidence": "The issue has no assignees, comments, or linked pull requests."
    },
    {
      "name": "ai-policy-compatible",
      "grade": "pass",
      "evidence": "docs/CONTRIBUTING.md contains workflow and testing requirements but no AI-assistance ban."
    },
    {
      "name": "starter-signals",
      "grade": "pass",
      "evidence": "The issue has good first issue and tier-1 labels and clearly states the expected configuration change."
    }
  ],
  "verdict": "accept"
}
```

## Eval iterations

**Run history**

Run 1 produced no agreement score because the official harness was invoked by
the default Python 3.8.2 interpreter and stopped at
`TypeError: 'type' object is not subscriptable`; the harness uses the Python
3.9+ annotation `set[str]`. Run 2 used Python 3.11, but every Sonnet request
returned `You've hit your individual spend limit · run /usage-credits to ask
your admin for a higher limit`, so the harness reported `agreement: 0/0
scored items` and refused to write a partial run. `eval-run.txt` remains
unmodified because a harness-generated complete run is required.

**Issue analysis**

No scored issue has a rubric verdict to compare with a gold label because the
Sonnet requests could not run. The harness output for every item, including
`issue-01`, was `ERROR (claude exited 1: )`; its direct CLI output identified
the spend-limit failure quoted above. I did not infer or record a verdict in
place of an unavailable model result.

**Check rationale**

`| available | In repo facts or the GitHub issue sidebar and thread, inspect
assignees, linked pull requests, and claim comments. In Path Review live mode,
apply the scope file's shared-issue house rule. | There is no assignee, no open
linked pull request, and no unaddressed claim comment from the last 30 days.
Closed unmerged pull requests do not fail this check. | required |`

I made availability required because an otherwise healthy issue is not a good
first contribution when another contributor is actively implementing it. The
Path Review exception is explicit so classroom collaboration does not make a
candidate fail solely because another student expressed interest.

**Trade-offs**

This availability check can reject a good issue after an unanswered recent
claim comment even when that contributor never submits a pull request. I
accept that false negative outside Path Review because it avoids duplicating
active work; the scoped classroom exception preserves collaboration for the
course repository.

## Selection rationale

**Selection rationale**

1. Issue #73 fits the available time because it is a focused documentation and
   configuration consistency fix in two named files. It is smaller and less
   risky than a behavior change across authentication or retrieval code.
2. The verdict correctly identified an active repository, a bounded request,
   and no current implementation competing for the work. Beyond the rubric, I
   weighed that the expected source of truth is already named (`core/config.py`),
   so I can verify the change without deciding a new API design.
3. Claiming should be straightforward because the issue has no discussion or
   assignment history. The only anticipated difficulty is confirming every
   documented provider variable and example remains consistent rather than
   fixing only the currently named key.
