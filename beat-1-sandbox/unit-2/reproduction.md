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

Jeremy-Tian

---

## Posted upstream

**Claim comment**

[TODO — not yet posted. Paste the comment permalink here, then the exact text you posted underneath it.]

**Reproduction comment**

[TODO — not yet posted. Paste the comment permalink here, then the exact text you posted underneath it.]

## Eval iterations

Answer all four sections. Quote source text directly; paraphrase does not satisfy these
fields.

**Run history**

- `agreement: 20/20 scored items  (bar: 18/20: PASS)`

This is the agreement line from the committed `eval-run.txt`, written by the harness at
`2026-09-28T02:54:13Z` against `rubric.md sha256:2796e09e0589d89c` and
`evidence-guide.md sha256:3366f7c106a36fcd`. That run also cleared the category floor:
`categories: clear-accept 8/8  disclosure 1/1  no-evidence 4/4  unfollowable-comms 3/3  wrong-target 4/4`.

**Package analysis**

`pkg-20` (source `ghostty-org/ghostty#13604`, category `disclosure`). My rubric decided
`reject`; the gold label is also `reject`.

This is the package that makes the disclosure category worth having, because every other
family in it is strong. The report carries a real environment (`Environment: ghostty 1.3.1
(release build, Fedora 42 RPM), GTK backend, GNOME 48 (Wayland), dark system scheme.`),
numbered steps with exact commands, and — unusually — a control run: the single-theme launch
answers `^[[?997;2n` and the conditional-pair launch answers `^[[?997;1n`, which is precisely
the contrast the issue describes. My first four checks all pass on it.

It fails on the fifth. The repo-facts block states ghostty's policy in full: `contribution
policy (CONTRIBUTING.md + AI_POLICY.md): strict AI rules. All AI usage in any form must be
disclosed, stating the tool used and the extent of the assistance`. Neither the claim comment
nor the repro report says anything about AI use. Because my disclosure clause lives inside a
`required` check rather than a preferred one, that single miss carries the verdict to
`reject` on its own, which is what the gold label wants. A rubric that folded disclosure into
a "comms quality" nice-to-have would have graded this package `accept` on the strength of its
evidence and lost the only package in the category.

**Check rationale**

Quoted exactly as it reads in `tools/repro-check/rubric.md`:

`| Repo conventions and disclosure are respected | issue thread, repo rules, contribution policy, and the claim/repro wording | Pass if the comment is specific to the issue, does not over-promise or speak as if the fix is guaranteed, and includes any required AI-use disclosure if the repo asks for it | required |`

Three things are deliberate here. First, the evidence column names the contribution policy
directly, so the check reads the repo's stated rules rather than a general sense of etiquette —
without that, there is nothing in the package to hold `pkg-20` against. Second, the disclosure
clause is conditional (`if the repo asks for it`), so it does not punish the many packages
whose repos have no AI policy; in the committed run the four `clear-accept` packages and the
rest of the accept set are unaffected by it. Third, the whole row is `required`, not
`preferred`. That is the part I care about most: disclosure is the kind of miss that reads as
minor next to a strong artifact, and weighting it as preferred would have let the strongest
evidence in the set outvote the repo's own rule.

I rejected two earlier shapes. A separate standalone "AI disclosure" row would have fired
`unclear` on every package whose repo has no AI policy, and `unclear` counts as fail under my
verdict rule, so it would have rejected most of the accept set. Judging the comment's tone or
length instead of its content would have been a structure-shaped check of exactly the kind the
rubric template warns against.

**Trade-offs**

Nothing changed in the final revision pass, and here is how I know: the committed run agrees
on all twenty scored packages and clears every category —
`categories: clear-accept 8/8  disclosure 1/1  no-evidence 4/4  unfollowable-comms 3/3  wrong-target 4/4`.
There was no disagreement row left to chase with `--only`, so no canary re-run was needed.

What the rubric gives up is visible in the conditional disclosure clause. Because the check
only fires when the repo states a policy, a package that uses AI heavily in a repo with no
written AI rule passes this check. I accept that: the check reads the repo's stated rules, and
inventing a disclosure requirement the project never asked for would make the tool disagree
with maintainers rather than with bad packages. The eval set has exactly one package in the
`disclosure` category, so this clause is also the thinnest-evidenced part of the rubric — one
package is not much of a sample, and I would expect it to be the first place a wider set
found a disagreement.

---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/repro-check/`.
