## Dedalo

> Turn code merges into sustainable open-source funding.

Open source runs on work that nobody is paid for. Dedalo closes that gap
inside the workflow that already exists: a merge into `main` is what earns,
and the payout is computed from git history rather than typed into a
dashboard.

```
git merges  ──▶  attribution  ──▶  payout plan  ──▶  settlement
(source of      (integer          (content-        (on-chain,
 truth)          weights)          addressed)       or simulated)
```

Everything up to settlement is pure and offline. The same repository and the
same `dedalo.toml` produce the same plan id on any machine, so a plan whose id
changed is a plan someone tampered with — and anyone can recompute a round and
check the numbers.

**What that buys a project**

- **Merge-to-Earn** — merged code earns transparent, crypto-native rewards for
  whoever wrote it, co-authors included.
- **Autonomous treasuries** — a share of every round stays with the project,
  so its budget grows with its activity.
- **Self-funding network** — a protocol fee flows to the network's own
  collective. It is funded by the flow it enables, not by grants.
- **CI/CD native** — it runs in your pipeline. No third-party dashboard, no
  invoices.

**→ [dedalo-org.github.io](https://dedalo-org.github.io/)** ·
**📖 [the handbook](https://dedalo-org.github.io/dedalo/)** ·
**📦 [docs.rs/dedalo](https://docs.rs/dedalo)**

### Projects

- **[dedalo](https://github.com/dedalo-org/dedalo)** — the protocol:
  attribution, payout plans, the hash-chained ledger, the claim contract, and
  the CLI and GitHub Action that drive them. Rust.
  [Handbook](https://dedalo-org.github.io/dedalo/) ·
  [API reference](https://docs.rs/dedalo).
- **[dedalo-nvim](https://github.com/dedalo-org/dedalo-nvim)** — attribution
  where the code is: who earns from the lines in front of you, and who wrote
  code the round would not pay. Lua.
- **[discussions](https://github.com/orgs/dedalo-org/discussions)** — questions,
  ideas and announcements for the organisation.

On-chain settlement is **not live**. The vault's rules are pure Rust with a
test per way it refuses, and the deployable that wraps them is unaudited and
undeployed; Dedalo holds no signing key and never signs. See
[how funds move](https://dedalo-org.github.io/dedalo/operating/multisig.html).

### Getting involved

Read [CONTRIBUTING.md](https://github.com/dedalo-org/.github/blob/main/CONTRIBUTING.md)
for how work lands here, each repository's own guide for its build and test
loop, and the handbook's
[development chapter](https://dedalo-org.github.io/dedalo/contributing/development.html)
for the three gates that catch people out. Questions belong in
[discussions](https://github.com/orgs/dedalo-org/discussions); bugs with a
reproduction belong in the issues of the repository they affect.

Security issues go through a private advisory on the repository concerned,
never a public issue and never a discussion — see
[SECURITY.md](https://github.com/dedalo-org/.github/blob/main/SECURITY.md).
