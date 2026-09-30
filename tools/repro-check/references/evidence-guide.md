# Evidence guide: where proof lives in a reproduction package

<!--
THIS IS THE PART YOU WRITE (new this week: Unit 1 handed you this file
finished; the scaffolding fades). The skill uses this guide as its map:
for every kind of proof a rubric check names, this file says WHERE to
find it in a package and WHAT GOOD LOOKS LIKE when you do.

Under each family heading below, write:

- Where it lives: the exact places to look. In an eval bundle (which
  section of the package: the issue context, the repo-facts block, the
  claim comment, the repro report and its parts). In live mode (where
  on GitHub or in the draft: the issue thread, the repo's docs, the
  student's draft comment).
- What good looks like: one or two sentences someone else could apply.
  Prefer observable conditions ("the versions named match what the
  issue targets, or the difference is called out") over adjectives
  ("environment is thorough").

A rubric check whose evidence this guide cannot locate is a check
nobody else can execute; the rubric swap showed you what that feels
like. Write the map you wish your grader had.
-->

## Environment

**Where it lives.** In an eval bundle, compare the issue's stated
environment and repo-facts block with the repro report's environment
line and any version/configuration details in its commands or output.
In live mode, compare the issue body, issue template, and linked
repository documentation with the draft repro comment.

**What good looks like.** Record the platform and tool or dependency
versions that could change the behavior, plus material configuration
such as a driver, shell, install source, build profile, or input. A
different environment is usable evidence only when the difference is
called out rather than silently treated as equivalent.

## Steps

**Where it lives.** Read the repro report's commands, input files, and
prose instructions against the issue's reported trigger. In live mode,
also use the issue body and repository's bug-report guidance to resolve
what the starting state and trigger must be.

**What good looks like.** The report supplies the starting state and
the action that activates the issue, including material flags, input,
or configuration. A stranger can perform the same attempt without
access to private files or omitted setup; a command that exercises a
different code path is not a reproduction.

## Behavior shown

**Where it lives.** Compare the issue's described failure and expected
behavior with the report's captured command output, logs, measurements,
screenshots, or observable UI result. The candidate's assertion alone
is not an artifact.

**What good looks like.** The artifact shows the issue's reported
symptom under the stated attempt: for example, the matching error,
wrong value, missing state, crash, or control comparison. A successful
launch, an unrelated parser error, or output from altered input does
not demonstrate the target behavior.

## Honesty

**Where it lives.** Read the claim comment and the report's
expected/actual conclusion alongside its steps and artifacts, then
compare all of them to the issue context.

**What good looks like.** A report separates observation from
inference and does not claim a root cause, broader impact, fix, or
successful reproduction beyond its evidence. A cannot-reproduce report
is good when it shows the attempt and result and identifies meaningful
environment or trigger differences that could explain the outcome.

## Comms

**Where it lives.** Compare the claim comment with the issue title/body
and read both comments against the repo-facts block in eval mode. In
live mode, use the issue thread, the repository's issue template,
contributing documentation, and stated AI-use policy.

**What good looks like.** A claim names the issue's particular behavior
or trigger and promises only the next investigation or report. Both
comments honor explicit repository requirements, including required
AI-assistance disclosure; generic permission requests, self-assignment,
unbacked timelines, and fix promises are not specific and honest.
