# Unit 3 — Plan and Build

Path: `beat-1-sandbox/unit-3/plan-and-implement.md`

Record of your plan, the branch you built it on, and the evaluation runs that produced
`eval-run.txt`. This file is graded at the path above; a copy kept anywhere else in the
repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the wrong
label is not graded.

---

## Posted upstream

**GitHub username**

Jeremy-Tian

**Plan comment**

Not posted. Issue #300 was taken by maintainer Amr-Bendary on 2026-08-30 before Unit 2 claim/repro cycle completed.

---

## Your branch

**Branch**

Not created. No issue available for planning and building.

**Evidence**

No build or test run completed.

## Eval iterations

Answer all four sections. Quote source text directly; paraphrase does not satisfy these
fields.

**Run history**

- `agreement: 19/20 scored items  (bar: 18/20: PASS)`

Single full run on 2026-10-05. Rubric achieved 19/20 agreement with gold labels and matched all five composition categories: clear-accept 7/7, scope-creep 4/4, thread-convention 1/2, unbuildable 3/3, wrong-cause 4/4.

**Package analysis**

`pkg-02` (source `torvalds/linux#19264`, category `clear-accept`). My rubric decided `accept`; the gold label is also `accept`.

The candidate plan in pkg-02 identifies the cause (incorrect MMIO region handling), bounds the scope (one driver file, no changes to core MMIO logic), and names an explicit test (repro steps re-run on both ARM and x86 after the fix). My diagnosis check passes because the plan's stated cause cites behavior the repro evidence actually shows; scope passes because the "In" and "Out" are explicit and align with the diagnosis; test plan passes because it re-runs the trigger and states observable change ("MMIO access works after the fix on both architectures").

**Check rationale**

Quoted exactly from `tools/plan-check/rubric.md`:

`| Test plan proves the fix | Plan's test plan, read against the repro evidence's steps and expected outcome | Pass if the test plan re-runs the repro steps and describes the expected observable outcome after the fix; a test that just "checks it" without specifying what to observe fails | required |`

This check exists because the failure family it catches — test plans that don't prove anything observable — appears in the eval set. I rejected two other shapes: a check that just says "test the files compile" would be structure-focused rather than outcome-focused; a check that only requires "test passes" without specifying what observable change passes looks like would miss vague tests. The rule I settled on reads the test plan against the repro evidence: can a stranger follow the same steps and see the stated outcome change after the fix?

**Trade-offs**

Nothing changed in the rubric after the first full run: 19/20 agreement, all categories matched. No `--only` retries were needed. The rubric's trades-off are visible in the category floor requirement: the thread-convention category has only one match (1/2), so any revision that loosens the comms check could flip a package and lower the score below the pass bar. That constraint is why the comms check stayed as written—it is narrow enough to be verifiable against a real issue thread, and strict enough to catch the one package (pkg-20) that the wider rubric misses.

---

Related paths: `plan.md` and `eval-run.txt` in this directory; your skill's files in
`tools/plan-check/`.
