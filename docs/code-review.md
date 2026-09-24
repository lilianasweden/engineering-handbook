# Code Review Standards

## Why Code Review?
Code review is our primary quality gate. Every PR must be reviewed by at least one engineer who did not write the code.

## Expectations

### As the author
- Keep PRs small — under 400 lines of changes ideally
- Write a clear description: what changed, why, how to test
- Link to the relevant GitHub issue
- Respond to all comments before merging

### As the reviewer
- Review within 1 business day (P0 fixes: within 1 hour)
- Use the labels: `approved`, `needs changes`, `question`
- Be specific — quote the line, suggest the fix
- Approve only when you are confident the code is correct and safe

## Merge Rules
- At least 1 approval required (2 for changes to shared platform code)
- All CI checks must be green
- No unresolved comments
- Branch must be up to date with `main`

## Tips
- If a PR is too large to review properly, ask the author to split it
- Security-sensitive code (auth, payments, PII) requires a senior engineer review
