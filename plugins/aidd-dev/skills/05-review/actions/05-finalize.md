# 05 - Finalize

Judge the round the axes filled, and check it before it ships.

## Input

The round the axes filled.

## Output

The `Verdict` field of the round in `review.md`, and a round matching its declared shape.

## Process

1. **Judge.** Set `Verdict` per [review-rubric.md](../references/review-rubric.md).
2. **Check.** Verify the round against the shape [report-contract.md](../references/report-contract.md) names, and fix what breaks.

## Test

| Case | Pass |
| --- | --- |
| Two axes ran, one major between them | `Verdict` reads `changes-requested` |
| A field or a list is missing | it is filled, or the run says why it cannot be |
| The run ends | no file of the reviewed code is patched |
