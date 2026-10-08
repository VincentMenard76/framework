# 01 - Prepare

Resolve what is reviewed and where it lands, then open this round.

## Input

The arguments, and the plan when one is named.

## Output

A round appended to the feature folder's `review.md`, its fields filled, and the diff the axes read.

## Process

1. **Resolve.** Resolve the diff and the report's folder per [report-contract.md](../references/report-contract.md).
2. **Open.** Append a round from the template `report-contract.md` names, filling `Date`, `By` from `git config user.name`, `Diff`, and `Axes` with the axes about to run.
   - `Rounds` counts the round sections, and `Started` is round 1's date, kept by every later round.
   - Take the new number from the `## Round` headings, never from their bodies, and draw the id once so two rounds appended in parallel still differ.
3. **Hand over.** Name the diff and the round the axes write into.

## Test

| Case | Pass |
| --- | --- |
| A fresh report | round 1 appended, `Started` set to its date |
| A report holding two rounds | a third appended, `Rounds` reading 3, the first two unchanged |
| A run naming one axis | `Axes` names that axis alone |
| The run ends | no file of the reviewed code is patched |
