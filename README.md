# Release Actions acceptance tests

This repository exercises [Release Actions](https://github.com/hainuoli/release-actions)
with real GitHub events and disposable demo versions.

1. Open and merge a categorized PR; confirm its entry appears in
   [release notes](docs/release-notes.md).
2. Run **Prepare Release** on main with an unused version and the intended date.
3. Review the generated release PR and its `release` label, then merge it.
4. Push an annotated tag at the reviewed main commit.
5. Confirm **Publish Release** publishes only that version's notes.
6. Rerun preparation before merge and publication after release; confirm no duplicates.

The workflows pin the action to a reviewed full commit SHA. The default workflow
token is sufficient for the demo after enabling workflow PR creation. It does not
trigger ordinary PR CI on generated PRs; use a scoped `RELEASE_ACTIONS_TOKEN` or
close and reopen the PR with a user account when checks are required.
