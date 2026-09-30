# Rubric: is this reproduction package ready to post?

<!--
THIS IS THE PART YOU WRITE. The skill in SKILL.md executes whatever
checks you define here. It ships empty on purpose: the judgment is your
work.

A filled rubric must contain:

1. At least one row in the checks table. Each row needs all four
   columns:
   - Check: a short name (used in the output JSON).
   - Evidence: exactly what to look at, and where in the package. Name
     the part (the claim comment, the repro report's environment
     record, the artifacts read against the issue's description, the
     repo-facts block) or a location from your
     references/evidence-guide.md. "The report" is not a source; "the
     output excerpt read against the error the issue describes" is.
   - Pass condition: a decision rule about the OUTCOME that someone
     else could apply and get your answer. Judge the thing itself (does
     the artifact show the issue's behavior?), never the write-up's
     shape (how many steps it has, how long it is, whether it uses a
     template's headings). Structure-shaped checks are what make
     graders disagree with themselves.
   - Weight: `required` (a fail here holds the package) or `preferred`
     (never changes the verdict).

2. A verdict rule below the table: how the check grades combine into
   accept (ready) or reject (hold), including how `unclear` is
   treated. The verdict space is binary. If you write no rule for
   `unclear`, the skill treats it as fail.

Cover what actually gets bad packages posted. The lecture named the
proof families: the environment is recorded, the steps are complete
and followable, the behavior shown matches the issue (not an adjacent
one), the outcome is stated honestly (an evidenced cannot-reproduce is
a pass, a confident wrong-target is not), and the words respect the
repo's conventions. A rubric that ignores a family will fail eval
packages designed around that family.
-->

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| Claim is specific and bounded | Read the claim comment against the issue title/body and the repo-facts block's contribution policy. | The claim identifies the issue's concrete behavior or trigger and states a bounded next investigation step. It does not promise a fix, timeline, assignment, or priority; any stated reproduction, conclusion, or diagnosis is supported by the package's report and artifacts. In a claim-only draft, it does not assert completed reproduction or a diagnosis. | required |
| Attempt is placeable and repeatable | Read the repro report's environment record and reproduction steps against the issue's stated target and the repo-facts block's bug-report requirements. | A stranger can establish the material starting conditions, run the reported attempt, and place its result: versions/platform/configuration that could affect the issue are recorded, and any material difference from the issue is named. The steps include the trigger rather than only a setup or an adjacent command. | required |
| Artifact demonstrates the reported outcome | Read the repro report's shown output, log, screenshot description, or other artifact against the issue's described behavior and expected/actual outcome. | The shown artifact demonstrates the same behavior the issue describes under the reported attempt, not merely a related error, a successful setup, or a differently-triggered failure. | required |
| Conclusion matches the evidence | Read the report's conclusion, expected/actual statements, and any cannot-reproduce explanation against its steps and artifacts. | The report states only what its evidence establishes. A reproduced result accurately identifies the observed behavior; an honest cannot-reproduce is acceptable when it shows the attempt, result, and material differences or plausible missing conditions. Unsupported certainty, root-cause claims, and generalizations fail. | required |
| Repository conventions are met | Read both candidate comments against the repo-facts block's bug-report template and contribution policy, including any AI-use policy. | The comments meet any stated mandatory communication or disclosure requirement. If the policy requires AI-assistance disclosure, the comments disclose it; if it does not, no disclosure is required. | required |

## Verdict rule

Accept a full package only when every required check passes. Reject it
when any required check fails or is unclear. For a claim-only draft,
grade only the claim-specific and repository-conventions checks; the
reproduction checks are `unclear` because they are not yet applicable
and do not participate in that claim-only verdict.
