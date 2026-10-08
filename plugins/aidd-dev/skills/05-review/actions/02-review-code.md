# 02 - Review Code

Grade the changed lines on clean code, and record each finding.

## Input

The changed lines prepare resolved.

## Output

The round's `Findings` lines, kind `code`, each rated and keyed on a changed `file:line`.

## Process

1. **Read.** Read every changed line for naming, structure, complexity, smells and error handling.
   - No runtime checks, and rule conformance belongs to the relevancy lens.
2. **Rate.** Rate one finding per issue per [review-rubric.md](../references/review-rubric.md).
   - Kind, one of: `standards`, `architecture`, `code-health`, `security`, `error-handling`, `performance`, `frontend`, `backend`.
3. **Record.** Append one `Findings` line per finding, keyed on its `file:line`.
   - Nothing found: leave the list out.

## Test

| Case | Pass |
| --- | --- |
| An issue is found | one `Findings` line, kind `code`, rated and keyed on a changed `file:line` |
| The diff is clean | no `Findings` list in the round |
| The run ends | no file of the reviewed code is patched |
