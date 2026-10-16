# homebrew-tap

Homebrew casks for [LennardGeissler](https://github.com/LennardGeissler)'s tools, on macOS and Linux.

```sh
brew install --cask lennardgeissler/tap/blindbucket
```

Homebrew adds the tap on first use; `brew upgrade` picks up new releases from then on.

| Cask | What it is |
|---|---|
| [blindbucket](https://github.com/LennardGeissler/blindbucket) | A transparent S3 encryption gateway. Installs the binary from the release archive and its shell completions for bash, zsh and fish. Available from the first release after 1.4.0. |

## How the casks get here

Nobody edits them by hand. Each cask in `Casks/` is written by the release
workflow of its project when a version is tagged: goreleaser points it at that
release's archives and records their SHA-256, which Homebrew checks before
installing. It lands on a branch first and moves to `main` only once the
release is published, because a draft release's archives cannot be downloaded
yet. The workflow writes here with a deploy key that can reach this repository
and nothing else.

## Not notarised by Apple

The binaries are not signed or notarised by Apple. Homebrew quarantines what a
cask downloads, and macOS would then refuse to run it, so each cask removes the
quarantine from its binary after installing, and says so. What vouches for the
download instead is the SHA-256 in the cask and the release's provenance
attestation. To check the archive Homebrew installed from:

```sh
gh attestation verify "$(brew --cache --cask lennardgeissler/tap/blindbucket)" --repo LennardGeissler/blindbucket
```

Issues and changes belong in the project the cask is for, not here.
