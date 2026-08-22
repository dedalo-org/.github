# Contributing

The organisation-wide defaults. Each repository's own `CONTRIBUTING.md`, when
it has one, is more specific and wins — this file is what applies everywhere.

## Before you write code

For a bug fix, just send the pull request. For anything that changes an
interface, a data format, or what a program pays out, open an issue first and
agree on the shape. A rejected design is much cheaper as a paragraph than as a
finished branch.

## Development environment

Every repository here pins its toolchain with Nix. With Nix installed:

```bash
nix develop            # or `direnv allow` once, if you use direnv
```

That gives you the exact compiler and tools CI uses. Without Nix, install
whatever the repository's pinned toolchain file names.

Before opening a pull request, run the repository's full local gate — usually
`nix flake check`, which runs the same checks CI does. If it passes locally,
CI will pass.

## Branches and commit messages

`main` is always releasable, and every change lands through a pull request.
Work on short-lived branches named for what they do — `feat/…`, `fix/…`,
`docs/…`, `ci/…` — and delete them once merged.

Pull request titles follow [Conventional Commits](https://www.conventionalcommits.org).
Because pull requests are squash merged, **the title becomes the changelog
entry**, so write it for someone reading the release notes:

```
feat(cli): add `dedalo identity export`
fix(money): keep dust with contributors when a weight is zero
docs: explain how the protocol fee funds the network
```

Anything that changes what people are paid — amounts, plan ids, a fee split —
is a breaking change even when it compiles. Say so with `BREAKING CHANGE:` in
the commit body.

## What a good pull request looks like

- **One concern per PR.** A refactor and a behaviour change in the same diff
  are two pull requests.
- **Behaviour changes carry tests.** Especially the awkward cases: zero,
  one element, amounts that do not divide evenly.
- **Public API changes carry documentation.** An undocumented public item is
  treated as an incomplete change.
- **Commit messages say why.** The subject is the change; the body is the
  reason it is the right one.
- **Co-authors get credit.** Use `Co-authored-by:` trailers. In this
  organisation they are not a courtesy — they are what splits a payout between
  pair partners.

## Review

Maintainers review for correctness first, then for whether the change fits the
design. Expect questions; they are about the code. A pull request that sits
unreviewed for a week is fair game to ping.

## Security

Never report a vulnerability in a public issue or pull request. See
[SECURITY.md](SECURITY.md).

## Conduct

Participating means agreeing to the [code of conduct](CODE_OF_CONDUCT.md).
