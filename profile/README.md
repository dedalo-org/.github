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

### Projects

- **dedalo** — the protocol: attribution engine, payout planner, settlement
  backends, and the CLI and GitHub Action that drive them. Private while the
  distributor contract is unaudited; it opens up before anything can move funds
  on its own.

### Getting involved

Read [CONTRIBUTING.md](https://github.com/dedalo-org/.github/blob/main/CONTRIBUTING.md)
for how work lands here, and each repository's own guide for its build and test
loop. Security issues go through a private advisory on the repository
concerned, never a public issue — see
[SECURITY.md](https://github.com/dedalo-org/.github/blob/main/SECURITY.md).
