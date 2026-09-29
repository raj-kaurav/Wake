# Git Workflow

**Phase:** 4 — Engineering Standards
**Status:** Draft for review
**Note:** Describes the workflow for **future** implementation. Phase 4
does not add git hooks or CI.

---

## Branches

- `main` is protected once implementation starts.
- Work branches: `cursor/<short-topic>-<suffix>` in this environment, or
  `<type>/<short-topic>` later (`feat`, `fix`, `docs`, `test`, `chore`).
- Do not commit implementation of the app on a documentation-only phase
  branch without authorization.

## Commits

Imperative mood, one concern. First line states the outcome.

```
Add MicroStart transition tests for the 20-second boundary
```

Body, when needed, references a doc or decision: `BehaviorArchitecture`,
`D-004`, `P8`.

## Pull requests

Required for any change that touches domain rules, content schema,
analytics events, or notification types.

PR description includes:

- What changed
- Behavioral mapping (six fields) if behavior-adjacent
- Product Decision or architecture doc link
- Test notes (or why tests are not applicable)
- Privacy impact (none, or what field was added)

## Review

At least one reviewer once a team exists. Author does not solely approve
architectural changes. Use `CodeReview.md`.

## Merge

Squash or merge commit is a team choice **left open** until implementation
(no preference forced). Forbidden: merging a PR that adds a prohibited
module even if tests pass.

## Documentation

If the change alters architecture, update the architecture doc and add a
Product Decision Log entry **in the same change**. Do not let code become
the spec.

## Change categories

| Category | Examples |
|---|---|
| Docs | Standards, copy in docs |
| Domain | MicroStart, FreshStart, content rules |
| Platform | Widget renderer, Speak Time adapter |
| Privacy | Token, logging, analytics schema |
| Spike | H13–H15 evidence write-up, not a silent framework lock |
