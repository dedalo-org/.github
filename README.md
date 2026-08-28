# .github

Organisation-wide defaults for [`dedalo-org`](https://github.com/dedalo-org).

| File | What GitHub does with it |
| --- | --- |
| `profile/README.md` | Rendered on the organisation's public profile page |
| `CODE_OF_CONDUCT.md` | Default code of conduct for repos that ship none |
| `CONTRIBUTING.md` | Default contributing guide |
| `SECURITY.md` | Default security policy, and the "Report a vulnerability" text |
| `SUPPORT.md` | Default support pointer |
| `.github/ISSUE_TEMPLATE/` | Default issue forms |
| `.github/PULL_REQUEST_TEMPLATE.md` | Default pull request template |
| `FUNDING.yml` | The **Sponsor** button on every repository — [Open Collective](https://opencollective.com/dedalo). Needs each repository's *Sponsorships* feature switched on as well; that box is UI-only |

These are **fallbacks**. A repository that ships its own copy of any of these
files overrides the version here — which is what you want for anything
project-specific, such as a security policy that has to describe that
project's own threat model.

## The question to ask when reviewing these

**Not "is this good for `dedalo`" — "is this good for the repository that has
nothing else."**

`dedalo` overrides most of these files, so reading them with `dedalo` in mind
is reading them for the one repository they mostly do not apply to. What they
actually govern is `dedalo-nvim`, the site repositories, `discussions`, and
whatever is created next — a Lua plugin, an HTML page, and a repository that is
nothing but a discussions host.

That framing is what makes these files reviewable, and it is what catches the
mistakes they collect. Three found by asking it:

- `CONTRIBUTING.md` told everyone to run `nix develop` and `nix flake check`.
  **No repository here has a `flake.nix`** — the development environment lives
  in a private superproject one level up — so the instruction could not work
  anywhere, and had never worked.
- `CODE_OF_CONDUCT.md` sent conduct reports to **`dedalo`'s security advisory
  form**: the wrong instrument, from a document that governs every repository.
- `.github/ISSUE_TEMPLATE/config.yml` sent a vulnerability in `dedalo-nvim` to
  `dedalo`'s advisory form, for the same reason.

Each was invisible while reading as a `dedalo` maintainer, and obvious the
moment the question was "what does somebody filing an issue on `dedalo-nvim`
see".

## The leverage cuts both ways

A stale sentence here is stale in every repository at once, and nobody reading
it can tell it came from a default. So a change to any of these files is a
change to every repository that has no copy of its own — review it that way.
