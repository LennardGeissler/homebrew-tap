# homebrew-tap

Homebrew formulae for [LennardGeissler](https://github.com/LennardGeissler)'s tools.

```sh
brew install lennardgeissler/tap/blindbucket
```

Homebrew adds the tap on first use; `brew upgrade` picks up new releases from then on.

| Formula | What it is |
|---|---|
| [blindbucket](https://github.com/LennardGeissler/blindbucket) | A transparent S3 encryption gateway. Installs the binary and its shell completions for bash, zsh and fish. |

## How the formulae get here

Nobody edits them by hand. Each formula is written by the release workflow of its
project when a version is tagged: goreleaser points it at that release's archives
and records their SHA-256, which Homebrew checks before installing. The workflow
writes here with a deploy key that can reach this repository and nothing else.

Issues and changes belong in the project the formula is for, not here.
