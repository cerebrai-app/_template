# _template

Template repository for new cerebrai-app repositories.

## What's included

The standard GitHub Actions workflows, which call the shared composite actions in
[cerebrai-app/actions](https://github.com/cerebrai-app/actions):

| Workflow | What it does |
| --- | --- |
| [`claude.yml`](.github/workflows/claude.yml) | Runs Claude Code when someone mentions `@claude` |
| [`claude-code-review.yml`](.github/workflows/claude-code-review.yml) | Reviews every PR with the `code-review` and ponytail plugins |
| [`release-notes.yml`](.github/workflows/release-notes.yml) | Writes the GitHub Release notes for each `vX.Y.Z` tag with Claude Code |
| [`renovate.yml`](.github/workflows/renovate.yml) | Weekly self-hosted Renovate, configured by [`renovate.json`](renovate.json) to keep pinned actions current |

## Secrets

Set these at the repository or organization level:

- `CLAUDE_CODE_OAUTH_TOKEN` — for the Claude workflows, release notes included.
- `RENOVATE_APP_CLIENT_ID`, `RENOVATE_APP_PRIVATE_KEY` — for Renovate. Until they exist the job
  only prints a warning.

## Release notes

`release-notes.yml` runs when a `vX.Y.Z` tag is pushed or a release is published, and writes the
notes from the commits and pull requests since the previous version. Set its `about` input to a
sentence on what the repository is and who reads its releases. To write or rewrite the notes of an
existing tag, run the workflow by hand from the Actions tab.
