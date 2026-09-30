# Unit 2 — Claim and Reproduce

Path: `beat-1-sandbox/unit-2/reproduction.md`

Record of your claim and reproduction on the issue you chose in Unit 1, and of the
evaluation runs that produced `eval-run.txt`. This file is graded at the path above; a copy
kept anywhere else in the repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the wrong
label is not graded.

---

## Your identity upstream

**GitHub username**

AshankDsouza

---

## Posted upstream

**Claim comment**

https://github.com/codepath/pathreview-ai301-fa26-s1/issues/73#issuecomment-5904209108

Hi! I will verify the README and `.env.example` configuration mismatch described here against
`core/config.py`, then follow up with a reproduction report that records the repository revision,
steps, and observed settings.

**Reproduction comment**

https://github.com/codepath/pathreview-ai301-fa26-s1/issues/73#issuecomment-5904212254

Reproduction report

Environment: macOS 26.3.1; Git 2.30.1 (Apple Git-130); fork revision `f89c06f`.

Steps:
1. Clone the repository and check out revision `f89c06f`.
2. Run `grep -n "OPENROUTER_API_KEY" README.md`.
3. Run `grep -nE "LLM_PROVIDER|OPENAI_API_KEY|OPENROUTER_API_KEY|OPENROUTER_MODEL" .env.example`.
4. Run `grep -nE "llm_provider|openai_api_key|openrouter_api_key|openrouter_model" core/config.py`.

Observed:
- `README.md:24` tells users to add `OPENROUTER_API_KEY` to `.env`.
- `.env.example` lists `LLM_PROVIDER=mock` and `OPENAI_API_KEY`, but no
  `OPENROUTER_API_KEY` or `OPENROUTER_MODEL`.
- `core/config.py` defines `openrouter_api_key` and `openrouter_model` in addition to the OpenAI
  settings.

Expected: the README, `.env.example`, and `core/config.py` describe the same supported LLM
configuration.

Actual: a user following the README is instructed to set `OPENROUTER_API_KEY`, but the example
environment file neither documents that variable nor presents the OpenRouter provider/model
settings.

## Eval iterations

Answer all four sections. Quote source text directly; paraphrase does not satisfy these
fields.

**Run history**

Run 1 did not produce an agreement score. The full harness launched all 20 packages, but each
`claude -p --model sonnet` invocation exited before grading. A direct CLI check reported
`Failed to authenticate: OAuth session expired and could not be refreshed`. The harness therefore
reported `agreement: 0/0 scored items` and did not write a complete `eval-run.txt`. I did not
create or edit an eval transcript by hand.

**Package analysis**

I manually applied the uploaded rubric to `pkg-20`; this is not a harness result because the
authentication failure prevented model grading. The rubric's decision is **reject**, which matches
the gold label **reject**. The report's steps, environment, and artifacts are otherwise strong,
but the repo-facts block says Ghostty requires disclosure of all AI use and neither candidate
comment discloses it. The required `Repository conventions are met` check therefore fails: a
policy requirement is evidence, not a stylistic preference.

**Check rationale**

`| Artifact demonstrates the reported outcome | Read the repro report's shown output, log, screenshot description, or other artifact against the issue's described behavior and expected/actual outcome. | The shown artifact demonstrates the same behavior the issue describes under the reported attempt, not merely a related error, a successful setup, or a differently-triggered failure. | required |`

I chose this check because a report can be detailed while proving the wrong behavior. I rejected a
format-based rule such as requiring a fixed number of steps or a particular heading: those rules
reward polished prose without establishing that the reported issue actually occurred.

**Trade-offs**

The artifact check deliberately rejects adjacent failures. For example, it rejects a report whose
altered input produces a parser error when the issue is about a later crash, even though both
attempts fail. That can reject a useful early investigation when the reporter's exact environment
is unavailable, but accepting it would let a confident report misidentify a different defect as
the issue under review.

---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/repro-check/`.
