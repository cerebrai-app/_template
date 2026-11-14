# _template

Starting point for new cerebrai-app repositories.

## Workflows

| Workflow | What it does |
| --- | --- |
| [`claude.yml`](.github/workflows/claude.yml) | Runs Claude Code when someone mentions `@claude` |
| [`claude-code-review.yml`](.github/workflows/claude-code-review.yml) | Reviews every pull request |
| [`release-notes.yml`](.github/workflows/release-notes.yml) | Writes the GitHub Release notes for each `vX.Y.Z` tag with Claude Code |
| [`renovate.yml`](.github/workflows/renovate.yml) | Keeps pinned actions up to date |

The steps live in [cerebrai-app/actions](https://github.com/cerebrai-app/actions), pinned by commit
with the tag as a comment; Renovate keeps the pins current. The Claude workflows need the
`CLAUDE_CODE_OAUTH_TOKEN` secret.

For release notes, set `about` in `release-notes.yml` to a sentence on what the repository is and
who reads its releases. To write or rewrite the notes of an existing tag, run the workflow by hand
from the Actions tab.
