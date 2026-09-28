# Evidence guide: where proof lives in a reproduction package

## Environment

Where it lives: the environment section in the repro report, the issue's own stated target, and any repo-facts block or setup notes in the bundle. In live mode, it usually lives in the issue body and the draft claim/repro comment where the reporter names OS, shell, versions, package manager, and repo state.

What good looks like: the environment record names the versions and platform that matter to the issue, or states an explicit difference from the issue target. A package that says only "on my machine" or omits the runtime, driver, or package version is weak because a stranger cannot place the attempt.

## Steps

Where it lives: the repro report's ordered commands or numbered steps, plus any setup instructions the issue needs before the trigger. In live mode, the issue thread and the report are the place to line up the exact commands with the reported failure.

What good looks like: the steps start from a clear baseline, use precise commands or inputs, and end with the trigger the issue describes. A good report does not skip setup, hide a required config flag, or rely on a reader to infer what the output should look like.

## Behavior shown

Where it lives: the artifacts section in the repro report — stdout/stderr excerpts, log files, screenshots, exit codes, or a control run that shows the contrast. In eval bundles, this is usually the output blocks read against the issue description.

What good looks like: the artifact directly shows the reported symptom or a precise control that distinguishes it from an adjacent error. If the artifact shows a different exception, a syntax error, or a different version's behavior, the package is not proof of the issue.

## Honesty

Where it lives: the repro report's summary sentence and the claim comment's wording about what was observed. In live mode, it also sits against the issue's expected behavior and the user's update history.

What good looks like: the package says exactly what happened, whether it reproduced, whether it was a control run, and what differed from the issue's conditions. Honest packages say "I could not reproduce here" when the artifact doesn't match; they do not collapse a control result into a claimed reproduction.

## Comms

Where it lives: the claim comment, the repro comment, and the repo's stated contribution or policy docs. In live mode, check the issue thread and the project's policy for required formatting, AI-use disclosure, or contribution rules; in eval bundles, this often shows up in the repo-facts or claim/repro sections.

What good looks like: the comments are specific to the issue, do not over-promise or speak as if a fix is guaranteed, and include any required AI disclosure. Boilerplate assertions, vague "me too" comments, or promises that cannot be checked are not evidence and are not appropriate upstream wording.
