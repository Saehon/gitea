- Never assume, verify before claiming
- List development targets with `make help`
- Read relevant developer documentation in the `docs` folder
- PR descriptions: minimal, only what and why, no task or file listings. Include screenshots for UI changes, before and after when modifying existing UI. Aim for less than 1000 characters
- Reference issues and PRs by full URL, not by number
- Use Conventional Commits for commit messages and PR titles, plus Gitea's `enhance` type for user-facing enhancements
- Add an `Assisted-by: AGENT_NAME:MODEL_VERSION` trailer to commit messages, never `Co-Authored-By` or `Signed-off-by`
- Attribute agent authorship on one trailing line in issue and PR comments, never as a PR description section
- Never rewrite git history unless asked, update PRs with new commits and normal push
- Comments: write almost none, short and preferably same-line, explaining why for a future reader. Never narrate code, the change or the prompt. Preserve existing ones that still apply. If you need to write a paragraph-long comment, rethink your implementation, it is likely too complicated
- Add the current year to copyright headers of new `.go` files
- In `options/locale`, only edit `locale_en-US.json`, other locales are synced automatically
- In TS, use `!` instead of `?.`/`??` when a value always exists
- In Go, prefer to use modern language features wherever possible
- Prefer `tw-*` utilities over inline `style` and `flex-*` helpers over per-child `tw-ml-*`/`tw-mr-*` margins, falling back to `tw-*` where specificity requires `!important`
- Run `make fmt` after `.go` edits, `make tidy` after `go.mod` edits, `make generate-swagger` after API changes, and lint what changed with `make lint-go`, `lint-js`, `lint-css` or `lint-templates`
- Fix the cause rather than disabling a linter or weakening a test. Where unavoidable, use the narrowest scope with a trailing comment giving the reason
- Run single tests with `go test -run '^TestName$' ./modulepath/` for Go, `pnpm exec vitest <path-filter>` for TS and `GITEA_TEST_E2E_FLAGS='<filepath>' make test-e2e` for e2e
- Write the fewest, fastest tests covering the behavior, extending an existing one where possible. Prefer unit tests where logic is testable in isolation
- Aim for sub-2s per integration test and sub-4s per e2e test. Wait on a deterministic condition rather than `sleep`, and prefer semantic locators in e2e tests

<!-- PSEUDOCODE-SYSTEMS-THINKING v1 -->
## Pseudocode and systems thinking

Before material research or implementation work, read `RESEARCH_METHOD.md` and the nearest project instructions. Define the system boundary and write/update numbered pseudocode before changing the relevant workflow. Map material steps to actual implementation, independent checks and output evidence. Use `research-method/contract.template.json` without treating a completed template as verified execution. For a trivial edit, update only the affected step or note why the algorithm is unchanged. Preserve project-specific permissions, pauses, scientific results, attribution and release rules. Apply this method to all subprojects, keeping each project's own sources, algorithm and evidence record separate.
<!-- END PSEUDOCODE-SYSTEMS-THINKING -->
