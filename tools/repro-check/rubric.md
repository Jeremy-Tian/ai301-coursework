# Rubric: is this reproduction package ready to post?

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| Environment is recorded | claim comment and repro report environment section; compare against the issue's stated target (OS, runtime, package version, repo state, relevant config) | Pass if the package names the environment needed to match the issue, and any version or platform differences are explicitly described rather than silently assumed | required |
| Steps are rerunnable | repro report step list and commands; compare against the issue's trigger and known setup | Pass if a stranger could follow the steps from a clear starting state without guessing missing commands, files, config, or versions | required |
| Artifact shows the issue | issue body plus the repro report's output, logs, screenshots, or excerpts | Pass if the artifact directly shows the reported behavior or a control that cleanly distinguishes it from an adjacent error; unrelated output or the wrong symptom fails | required |
| Result is honest and scoped | claim comment and repro report result summary, including any cannot-reproduce language | Pass if the report says exactly what happened, matches the artifact, and does not claim a reproduced bug when the evidence is a different error or a different version/platform | required |
| Repo conventions and disclosure are respected | issue thread, repo rules, contribution policy, and the claim/repro wording | Pass if the comment is specific to the issue, does not over-promise or speak as if the fix is guaranteed, and includes any required AI-use disclosure if the repo asks for it | required |
| Smallest credible proof | repro artifacts and control results | Pass if the package gives the minimal relevant evidence needed to show the issue or a clear cannot-reproduce explanation; noise or a huge dump without signal is not a reason to fail if the essential evidence is still clear | preferred |

## Verdict rule

Accept if every required check passes. Preferred checks never change the verdict; they only help rank accepted packages. `unclear` counts as fail.
