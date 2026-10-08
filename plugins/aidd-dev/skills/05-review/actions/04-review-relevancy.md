# 04 - Review Relevancy

Judge whether the change belongs, and record each misfit.

## Input

The diff prepare resolved, the need it serves (the plan objective or the ticket), and the plan when in scope.

## Output

The round's misfit `Findings` lines, each under a lens (`fit`, `conform`, `rot`), tied to evidence.

## Process

1. **Gather.** Capture the need, and discover the project's declared rules at runtime.
   - A source absent: fall back cleanly, never hardcode a rule.
2. **Fit.** Flag drift from the real intent, end to end and not only the literal criteria, under lens `fit`.
3. **Conform.** Flag each violation of a declared rule or convention, naming the rule, under lens `conform`.
4. **Rot.** Flag duplication, over-engineering and incoherence, citing the site, under lens `rot`.
5. **Record.** Append one `Findings` line per misfit, keyed on its `file:line`, kind the lens.
   - A bare opinion is no finding: tie each to a rule, a duplication site, a smell or a named need-gap.
   - Nothing found: leave the list out.

## Test

| Case | Pass |
| --- | --- |
| A misfit is found | one `Findings` line, kind `fit`, `conform` or `rot`, tied to a `file:line`, a rule, a duplication site or a need-gap |
| The change fits | no `Findings` list in the round |
| The run ends | no file of the reviewed code is patched |
