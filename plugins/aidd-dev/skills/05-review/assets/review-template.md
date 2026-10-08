# Review: {{feature}}

- Rounds: {{n}}
- Started: {{yyyy-mm-dd}}

<!-- One section per round, appended. Criteria come from the plan; Findings are defects no criterion covers. Drop this comment. -->

## Round {{n}} · r-{{4 hex characters}}

- Date: {{yyyy-mm-dd}}
- By: {{git config user.name}}
- Diff: `{{base}}...{{head}}`{{ plus the working tree, when it held changes}}
- Axes: {{the axes that ran, from code, functional, relevancy}}
- Verdict: {{verdict}}
- Score: {{n_met}}/{{n_plan}} met, {{n_unmet}} unmet, {{n_out}} out of the diff, or not scored

### Criteria

- [x] {{criterion met}} — {{file:line}}
- [ ] {{criterion unmet}} — {{gap}}
- [x] {{criterion no diff could show}} — not-applicable, {{why}}
- Out of the diff: {{phase-name}} ({{n}} criteria)

### Findings

- `{{file:line}}` : {{issue}} → {{fix}} — {{🔴 critical | 🟡 major | 🟢 minor}}, {{kind}}

<!-- Every placeholder is replaced by observed data, and a list no axis of this round owns is left out. One left standing is a bug. -->
