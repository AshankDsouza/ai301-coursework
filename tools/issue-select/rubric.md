# Rubric: is this a good first issue?

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| maintainer-active | In the bundle's repo-facts block, inspect the last five default-branch commits and the maintainer first-response sample; in live mode, inspect the same GitHub commit history and recently updated issues. | At least two of the last five default-branch commits are human-authored and dated within 90 days of the bundle capture date (or today in live mode), or a maintainer responded to a sampled issue within 30 days. | required |
| repo-in-use | In the repo-facts block or GitHub sidebar, inspect archived status, latest release, and last push. | The repository is not archived and either its latest release or its last push is within 180 days of the bundle capture date (or today in live mode). | required |
| newcomer-bounded | Read the issue body and comment thread. | The issue requests one implementable change, is not a support question, umbrella/tracking issue, or unresolved design discussion, and no maintainer says it requires a core-internals or parser-wide change. | required |
| available | In repo facts or the GitHub issue sidebar and thread, inspect assignees, linked pull requests, and claim comments. In Path Review live mode, apply the scope file's shared-issue house rule. | There is no assignee, no open linked pull request, and no unaddressed claim comment from the last 30 days. Closed unmerged pull requests do not fail this check. | required |
| ai-policy-compatible | Read the contribution-policy entry in repo facts or the repository contribution documentation. | The policy is silent about AI assistance or allows it with conditions; fail only for an explicit ban on AI-generated or AI-assisted contributions. | required |
| starter-signals | Read the issue labels and body. | The issue has a `good first issue` or `tier-1` label, or it includes a clear expected outcome or reproduction/test detail. | preferred |

## Verdict rule

Accept only if every required check passes. A required `unclear` counts as a
failure. Preferred checks never change the verdict; they only rank accepted
issues.
