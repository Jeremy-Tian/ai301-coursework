# Procedure: how this skill grades a plan package

<!--
THIS IS THE PART YOU WRITE, and it is a new kind of part. Weeks 1 and
2, SKILL.md carried a numbered workflow and you only wrote judgment
files. This week the workflow is gone from the frame: SKILL.md says
"execute procedure.md", and these are the operating steps you author.
The machinery is in your hands now.

Your operator swap is the design brief. When your executor stalled
because your rubric said WHAT to decide but not HOW to find the
evidence, that was a procedure gap. This file is where those gaps get
closed: a complete procedure lets someone who has never seen a plan
package before (a groupmate, or the skill itself) grade one exactly the
way you would.

Under each stage heading below, write the concrete steps for that
stage. The one-line note under each heading says what a complete
procedure must decide there. Write steps, not intentions: "read the
repro evidence before the plan, and note what behavior it pins down"
is a step; "understand the context" is a wish.
-->

## Read order

1. Read the repro evidence section first (the reproduction from unit 2) to ground what the plan is responding to: what behavior was observed, under what environment and steps, and what the issue reports.
2. Read the candidate plan in full, noting its diagnosis (cause), scope (what changes and what doesn't), approach, and test plan sections.
3. Read the candidate plan comment to check tone and specificity against the thread and repo conventions.

The order matters because the checks will compare the plan against what the evidence actually shows, not against what the plan claims it shows. Reading the evidence first prevents the plan's framing from occluding the repro.

## Evidence gathering

For each check, gather exactly what the rubric names:

1. **Diagnosis matches evidence**: From the repro evidence section, extract the exact observed behavior (what the issue shows) and the root cause the evidence points to. From the plan, extract the stated cause. Compare them directly.
2. **Scope is bounded**: From the plan, locate the "Change" statement (what will be modified) and "Out" statement (what will not be modified). From the repro evidence, note what files and components are involved. From the diagnosis check, note whether the stated cause matches the scope boundaries.
3. **Test plan proves the fix**: From the repro evidence, extract the exact steps and the expected observable outcome. From the plan, extract the test plan section. Compare step-by-step whether the plan re-runs the same trigger and describes the observable state change.
4. **Plan is executable**: From the plan's approach section and files-to-touch list, extract concrete steps, file paths, and module names. Note any hand-waving, vagueness, or references to "obvious" changes.

## Check execution

1. Execute the checks in order: diagnosis, scope, test plan, executability.
2. For each check, apply the pass condition stated in the rubric:
   - **Diagnosis**: pass if diagnosis matches evidence and does not contradict it; fail if it addresses only the symptom or contradicts what the evidence shows.
   - **Scope**: pass if the change is bounded, the "In" and "Out" are explicit, and they align with the diagnosis; fail if scope creep, vague boundaries, or misalignment.
   - **Test plan**: pass if the test re-runs repro steps and states the expected observable outcome; fail if it is vague ("check it works"), does not re-run the trigger, or specifies no observable change.
   - **Executability**: pass if a stranger could start implementing; fail if hand-wavy or unclear.
3. If evidence for a check is genuinely absent (e.g., the plan has no test plan section), grade unclear and note the absence.
4. Do not re-grade a check once graded unless the evidence gathering revealed a fact you missed.

## Verdict assembly

1. Count the required checks (diagnosis, scope, test plan). If all three pass, the verdict is **accept**. If any required check fails or is unclear, the verdict is **reject**.
2. Preferred checks (executability) never change the verdict; they only rank accepted plans.
3. Unclear counts as fail per the verdict rule.
4. Output the check grades and the verdict. For the deciding check (the first required check to fail or be unclear), quote the evidence that determined it.
