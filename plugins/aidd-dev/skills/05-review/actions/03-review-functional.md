# 03 - Review Functional

Trace the diff against the plan's acceptance criteria, one box each.

## Input

`plan.md`, its phase files with their criteria and their `## Architecture projection`, and the diff prepare resolved.

## Output

The round's `Criteria` list and `Score` field.

## Process

1. **Read.** Take the plan, or ask for the acceptance criteria.
   - None to be had: `Score: not scored`, and no `Criteria` list.
   - Static only: no app run, no browser.
2. **Trace.** Walk the plan's phases in order, writing each in its place.
   - A phase whose projected files the diff leaves untouched: no box, one `Out of the diff:` line with the plan's phase name and its criteria count. A phase projecting no file is traced instead, never out of the diff: it has no projected file to leave untouched.
   - A criterion unmet or partial: `[ ]` naming the gap, and no `Findings` line.
   - A criterion whose subject is absent from the work: `[ ]`, a gap like any other.
   - A criterion whose subject is there and whose property no diff could ever show: `[x]` reading `not-applicable`.
3. **Score.** Count over the plan's whole criteria total: those checked, those left `[ ]`, and those out of the diff, which sum to it.
   - A `not-applicable` criterion counts as met and says so on its line.
4. **Record.** Write boxes and fields, never prose.

## Test

| Case | Pass |
| --- | --- |
| A plan of 6 criteria, the diff touching one phase of 2 with 1 met | `1/6 met, 1 unmet, 4 out of the diff`, and one `Out of the diff:` line per untouched phase, in plan order |
| A name or label echoing the criterion, with no behaviour behind it | `[ ]` naming the gap |
| A criterion unmet | one `[ ]` line naming its gap, and no `Findings` line |
| A criterion whose subject is absent | `[ ]` naming the gap |
| A criterion whose property no diff could show | `[x]` reading `not-applicable`, counted as met |
| No plan and no criteria given | `Score: not scored`, and no `Criteria` list |
| A second round over the same plan | every box follows the current diff, none carried from the earlier round |
| The run ends | no file of the reviewed code is patched |
