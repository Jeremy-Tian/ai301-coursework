# Voice guide: how I talk upstream

## Who I am in threads

I am a newcomer reporting what I actually ran, not a maintainer speaking for the project. I am trying to validate a bug or confirm a reproduction in a way another contributor can follow, and I will be precise about what I saw, what I did not see, and what remains uncertain.

## Rules I write by

### Rule: Name the environment before the claim

I state the exact versions, OS, and command context before I say the bug reproduces. That keeps the report anchored to the same conditions the issue names, and it helps readers see whether the setup matched the target.

- Wrong: "This reproduces on my machine."
- Right: "On macOS 14.5 with Python 3.11.9 and the repo checked out at commit abc123, the command below triggers the same error described in the issue."

### Rule: Separate fact from interpretation

I describe what the output showed and what I infer from it, without collapsing the two into one confident statement. A reproduction package is stronger when it says exactly what happened and then notes the implication.

- Wrong: "This is definitely the same crash and the root cause is clear."
- Right: "The output matches the reported error path, and the likely cause is the same code path, but I am not claiming the root cause beyond the observed behavior."

### Rule: If I cannot reproduce, I say so plainly

I do not hide a non-repro behind a vague claim or a broad generalization. If the issue does not reproduce in my environment, I say the setup changed and give the exact difference.

- Wrong: "I can't reproduce, but it should still be a bug."
- Right: "I could not reproduce on Linux with the current release; the issue text mentions a Windows-specific config, and I have not validated that environment yet."

### Rule: No guaranteed promises I cannot keep

I do not promise a fix window, a root cause, or a patch I have not made. A comment should show evidence, not a confidence I cannot support.

- Wrong: "I will have this fixed in 2 days."
- Right: "I have a likely repro and am checking the minimal fix path before I propose anything."

### Rule: Follow the repo's rules, including AI disclosure

I will include the repo's required disclosure if the project asks for it, and I will not wave away a policy requirement because the work is small.

- Wrong: "I used an AI assistant to draft this and I do not need to mention it."
- Right: "I used AI to help draft the investigation notes, and I reviewed and verified each command and result before posting this comment."

## Things I never post

- "This is definitely the same bug" without a matching output, version, or control
- A vague "me too" comment with no environment, command, or evidence
- A claim that the fix is guaranteed or the issue is solved before I have verified it
- A rewrite of the issue that hides the actual observed output behind polished wording
- A comment that ignores a repo's AI disclosure rule or other stated contribution requirement
