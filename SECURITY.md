# Security policy

This is the organisation-wide default. Repositories that handle money or keys
ship their own `SECURITY.md` with a concrete threat model — read that one when
it exists, because it defines what counts as a vulnerability there.

## Reporting a vulnerability

**Do not open a public issue.** Report privately through GitHub Security
Advisories on the affected repository, for example
[dedalo](https://github.com/dedalo-org/dedalo/security/advisories/new).

Please include:

- what an attacker or a mistake can cause, concretely — in amounts, if money
  is involved;
- steps to reproduce, ideally as a failing test;
- the version or commit you tested.

You will get an acknowledgement within 72 hours and an assessment within seven
days. We will credit you in the advisory unless you prefer otherwise.

## What we treat as a security issue

Beyond the usual — memory safety, injection, privilege escalation, secret
disclosure — anything in this organisation that:

- causes funds to move to the wrong place, in the wrong amount, or twice;
- lets a payout plan's identity stay the same while its contents change;
- credits work to someone who did not do it;
- exposes, logs or persists a signing key.

## Scope

Supported: the latest release and the `main` branch of each repository.

Out of scope: the security of chains, wallets, RPC providers or funding
platforms themselves; misconfiguration in third-party repositories that use
our tools; and key management on a user's own machine.
