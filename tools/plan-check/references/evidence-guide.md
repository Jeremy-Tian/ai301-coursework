# Evidence guide: where evidence lives in a plan package

<!--
THIS IS THE PART YOU WRITE (second week running: the judgment files
stay in your hands). The skill uses this guide as its map: for every
kind of evidence a rubric check names, this file says WHERE to find it
in a plan package and WHAT GOOD LOOKS LIKE when you do.

Under each family heading below, write:

- Where it lives: the exact places to look. In an eval bundle (which
  section of the package: the issue context, the repro-evidence block,
  the candidate plan's scope statement or test plan, the plan comment,
  the repo-facts block). In live mode (where on GitHub or in the
  draft: the issue thread, the student's posted repro comment, the
  repo's docs, the draft plan and comment).
- What good looks like: one or two sentences someone else could apply.
  Prefer observable conditions ("the stated cause cites behavior the
  repro evidence actually shows") over adjectives ("diagnosis is
  solid").

A rubric check whose evidence this guide cannot locate is a check
nobody else can execute, and this week that cuts twice: your
procedure.md tells the skill WHEN to gather each family, and this
guide tells it WHERE. Write the map you wish your executor had.
-->

## Diagnosis and grounding

Where it lives: the plan's "Cause:" statement or opening diagnosis section, read against the "Repro evidence" section's observed behavior and any log or error output shown.

What good looks like: the stated cause directly explains what the repro evidence shows—not what the issue title suggests or what seems obvious from the symptom, but what the actual reproduction pinned down. "The post-push refresh scope just misses the branch-commits context" matches evidence showing the view not updating after push; "the UI is not fast enough" does not.

## Scope

Where it lives: the plan's "Change:" and "Out:" statements (or "In:" and "Out:" sections), and the list of files the plan will touch, read against what the issue names and what the diagnosis requires.

What good looks like: explicit boundaries. "Trigger a refresh of the commits context after a successful push. In: the push completion callback in pkg/gui/controllers/sync_controller.go adds the commits context to its post-push refresh scope. Out: any change to how push status is computed, or to other views' refresh behavior." defines what changes and what doesn't. "Fix the color issue" and "modify the controller as needed" are scope creep—the reader has to guess what "as needed" means and what collateral damage to accept.

## Executability

Where it lives: the plan's approach, the "Change:" statement, and the list of files to touch.

What good looks like: concrete steps and file paths someone unfamiliar with the codebase could follow. "Add the commits context to the post-push refresh scope in pkg/gui/controllers/sync_controller.go, at the same location where other contexts are added to the callback" lets you find the place; "make the context refresh" makes you ask "how do I know where?"

## Test plan

Where it lives: the plan's test section, read against the "Repro evidence" section's steps and expected behavior.

What good looks like: the plan re-runs the exact repro steps and names the expected observable change. "Repro steps above; at step 3 the color must flip without leaving the view" maps the test to the repro; "verify the fix works" does not say what you are looking for. A test that just checks the code compiles or a single field has a new value fails; a test that re-runs the user-facing trigger and observes the result passes.

## Honesty

Where it lives: any "Unknowns:", "Risks:", or "Deviations:" section in the plan, and between-the-lines anywhere the plan expresses uncertainty.

What good looks like: stated unknowns and risks, not false confidence dressed as diagnosis. "Will need to test both the branch-commits view and the main commits panel since both share the callback" is honest about what is untested; "this will obviously be fine" is not. After the build (week 4), a "Deviations:" section records what changed from the plan and why—a sign of adaptation, not failure.

## Comms

Where it lives: the plan comment, read against the issue's thread highlights (or the live thread), the repo-facts block's contribution policy, and any thread norms about plan style.

What good looks like: specific to the issue at hand, not boilerplate. "Reproduced on 0.64.1 (report above). The post-push refresh scope just misses the branch-commits context; plan is a one-change fix in the sync controller's push callback plus a manual check across the two commit views and force push. Will send the PR shortly; keeping it minimal given the review-bandwidth note in CONTRIBUTING" ties the plan to the issue, acknowledges the thread (maintainer bandwidth), and sets expectations. "Here's my plan to fix this issue" does not tie to anything and reads as generic.
