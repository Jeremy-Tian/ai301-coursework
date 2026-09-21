# Unit 1 — Issue Selection

Path: `beat-1-sandbox/unit-1/selection.md`

Record of the issue carried into Unit 2, and of the evaluation runs that produced
`eval-run.txt`. This file is graded at the path above; a copy kept anywhere else in
the repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the
wrong label is not graded.

---

## Selected issue

**Issue link**

https://github.com/Itqan-community/quran-apps-directory/issues/298

**Verdict output**

## Summary

| Check | Grade | Evidence |
|---|---|---|
| Repo is alive | pass | Not archived; last push 2026-07-31 and last 5 default-branch commits on 2026-07-13/07-14, all shortly before the 2026-08-05 capture date. |
| Scope is bounded | pass | Single concrete bug ("Submit App" hidden on desktop / non-functional on mobile) with three clear, checkable acceptance criteria — not a tracking list or open design debate. |
| No active claim or blocker | pass | "this issue: assignees: none; linked PRs: none" and 0 comments total — no claim or blocker present. |
| AI-workflow is allowed | pass | Contribution policy: "no statement on AI or contribution tooling" — no explicit ban. |
| Small, testable fix signal (preferred) | pass | Concrete acceptance criteria plus a "Where to start" pointer to `src/app/components/header/` and `src/app/components/mobile-menu/`, giving a clear, verifiable outcome. |

All required checks pass → **accept**.

```json
{
  "item": "issue-06",
  "checks": [
    {"name": "Repo is alive", "grade": "pass", "evidence": "last push to any branch: 2026-07-31; last 5 default-branch commits dated 2026-07-13/07-14; archived: no"},
    {"name": "Scope is bounded", "grade": "pass", "evidence": "Single bug (button hidden on desktop, broken on mobile) with three concrete acceptance criteria, no open-ended discussion"},
    {"name": "No active claim or blocker", "grade": "pass", "evidence": "\"this issue: assignees: none; linked PRs: none\"; 0 comments total"},
    {"name": "AI-workflow is allowed", "grade": "pass", "evidence": "contribution policy (CONTRIBUTING.md): no statement on AI or contribution tooling"},
    {"name": "Small, testable fix signal", "grade": "pass", "evidence": "Acceptance criteria are checkable (visible on desktop, functional in mobile drawer, works in RTL/LTR) and issue names exact files to start from"}
  ],
  "verdict": "accept"
}
```

---

## Eval iterations

Quote source text directly in each field below. Paraphrase does not satisfy them.

**Run history**

- `agreement: 13/20 scored items  (bar: 18/20: below the bar)`
- `agreement: 18/20 scored items  (bar: 18/20: PASS)`

**Issue analysis**

I picked `issue-06` as the written example in the final pass. My rubric decision was `accept`, and the gold label is also `accept`.

The reason the rubric landed there is visible in the bundle itself: `- this issue: assignees: none; linked PRs: none` and `Single bug (button hidden on desktop, broken on mobile) with three concrete acceptance criteria, no open-ended discussion` appear in the scored verdict output. That matches the gold label and the issue's clear, bounded fix with no active claim.

**Check rationale**

The check I kept and relied on most was the one that now reads:

`| Repo is alive | repo-facts block: last push to any branch, last 5 default-branch commits, latest release, and archived: flag | Pass if the repo is not archived and there is recent activity on the default branch or a recent release within the captured timeframe; a dead or abandoned repo fails | required |`

I kept it because the first-issue rubric needs a real project, not just a plausible bug. A dead repo is often a bad first contribution even when the bug description is clean, and the repo-facts block makes that visible in a straightforward, checkable way.

**Trade-offs**

The trade-off is visible in the final run output:

`issue-19  accept  reject   NO     failed: Scope is bounded, Small, testable fix signal (preferred)`

This rubric is intentionally stricter about bounded scope than a looser "issue looks fixable" heuristic. It accepts more false negatives in exchange for not taking a lot of stale, design-heavy, or unbounded work that still looks real at a glance.

---

## Selection rationale

**Selection rationale**

1. This issue fits my interests and the time available because it is a small UI bug with specific acceptance criteria and a narrow file path to inspect. It is small enough to reason about, and it is a good fit for a first contribution without requiring a large architecture change.
2. The verdict identified the right things: the repo is active, the issue is bounded, there are no active claims, and the project does not ban AI-assisted contribution. What I weighed outside the rubric was that the issue is concrete and easy to validate locally, even though the rubric cannot see that directly.
3. I expect the claim to be manageable: there are no linked PRs, no current assignee, and the acceptance criteria are clear. The main difficulty would be confirming the mobile and RTL/LTR behavior, but the issue remains a realistic first claim rather than a broad or unclear feature request.

---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/issue-select/`.
