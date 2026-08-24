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
| `.github/FUNDING.yml` | The **Sponsor** button on every repository — [Open Collective](https://opencollective.com/dedalo) |

These are **fallbacks**. A repository that ships its own copy of any of these
files overrides the version here — which is what you want for anything
project-specific, such as a security policy that has to describe that
project's own threat model. Keep the files here general enough to be true of
every repo in the organisation.
