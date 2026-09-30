# Voice guide: how I talk upstream

<!--
THIS IS THE PART YOU WRITE (new this week). Live mode reads this file
before any comment of yours goes out the door; eval mode ignores it
entirely, because your voice is yours and carries no gold labels.

This is not etiquette. "Be polite and concise" is advice for everyone
and therefore rules for no one. Write rules YOU need, in your own
words, each one concrete enough that the skill can hold a draft
against it and say which rule it breaks.

Three sections. Fill all three.
-->

## Who I am in threads

I am a student contributor verifying an issue before proposing any code.
I report what I ran and what I observed, and I treat the maintainers'
time and the issue's existing context as constraints rather than an
invitation to overstate my conclusions.

## Rules I write by

### Rule: Name the behavior

Tie my claim to the issue's actual trigger or symptom instead of using
interchangeable assignment language.

- Wrong: "I'd like to take this issue and send a fix soon."
- Right: "I'd like to verify the empty-search editor behavior and report the result with my environment and steps."

### Rule: Report observations, not certainty

State the command, artifact, and result before drawing a limited
conclusion. Do not turn one attempt into a diagnosis or a guarantee.

- Wrong: "This confirms the parser is broken everywhere."
- Right: "With the command below, I observed the reported parse error on macOS; I have not tested other platforms."

### Rule: Promise only the next checkable step

In a claim, promise investigation and a report, never ownership, a
deadline, a fix, or a priority decision.

- Wrong: "Assign this to me; I will have a guaranteed fix by Friday."
- Right: "I will try the reported trigger and follow up with the observed result."

### Rule: Keep the thread useful

Include the smallest evidence needed for another person to understand
what I tested, rather than encouragement, repetition, or speculation.

- Wrong: "+1, this is definitely the root cause and should be fixed urgently."
- Right: "I reproduced the missing result with the attached command output; the environment and expected/actual behavior are below."

## Things I never post

- A promise to fix, own, prioritize, or complete work by a date.
- A root-cause claim without evidence that directly supports it.
- A me-too confirmation without my own environment, steps, and result.
- An exaggerated claim about affected users, platforms, or severity.
