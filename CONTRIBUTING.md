# Contributing

Thank you for helping build Creativa Studio.

## Principles
- Preserve the permanent free core.
- Keep manual design independent of paid AI services.
- Prefer small, reviewable pull requests.
- Do not commit secrets, user data, or generated credentials.
- Do not add paid dependencies or infrastructure without explicit approval.
- Add tests for behavior changes.
- Keep accessibility and mobile workflows in scope.

## Before opening a pull request
1. Explain the problem and intended behavior.
2. Link the relevant issue or product requirement.
3. Run lint, type checks, tests, and production build.
4. Document limitations and any migrations.
5. Include screenshots or a short recording for UI changes.

## Data safety
All database changes must use reviewed migrations. Never drop, truncate, reset, or overwrite user data as a convenience.
