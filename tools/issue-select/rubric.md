# Rubric: is this a good first issue?

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| Repo is alive | repo-facts block: `last push to any branch`, `last 5 default-branch commits`, `latest release`, and `archived:` flag | Pass if the repo is not archived and there is recent activity on the default branch or a recent release within the captured timeframe; a dead or abandoned repo fails | required |
| Scope is bounded | issue body and comments; look for one concrete bug, feature, or docs task, not a tracking list, umbrella issue, or long design debate | Pass if the issue describes a single, realistic task with a clear outcome and the thread does not look like a still-open multi-part plan or unresolved product decision | required |
| No active claim or blocker | issue sidebar and thread: `assignees`, `linked PRs`, `claim comments`, and any comment saying someone is already working on it | Pass if there is no assignee, no open linked PR, and no current claim such as "I am working on this" or "@bot claim" that blocks new contributors | required |
| AI-workflow is allowed | repo-facts `contribution policy` and linked AI-use guidance | Pass if the repo does not explicitly ban AI-generated code or documentation; disclosure, testing, and review requirements are acceptable | required |
| Small, testable fix signal | issue body, reproduction steps, expected behavior, or a maintainer wording that defines the task | Pass if the issue has a concrete, small change to make and a realistic way to validate it; docs tasks or small features count when the home and outcome are clear | preferred |

## Verdict rule

Accept if every required check passes. Preferred checks never change the verdict; they only help rank accepted issues. `unclear` counts as fail.
