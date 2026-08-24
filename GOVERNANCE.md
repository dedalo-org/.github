# Governance

Dedalo asks projects to route money using rules this organisation writes, and
asks contributors to accept a payout computed by code it controls. Neither is a
reasonable ask without saying who decides things. This is that document.

It is an organisation default: it applies to every `dedalo-org` repository that
ships no `GOVERNANCE.md` of its own.

## Who decides

| Role | Who | What it means |
| --- | --- | --- |
| Maintainer | [@4137314](https://github.com/4137314) | Merges, releases, and holds the crates.io ownership |

One maintainer is the honest state today, and it is a weakness rather than a
structure. It is written here so that it is visible, and so that the first
thing a second maintainer does is edit this table.

A change that needs more than one person is named as such below rather than
assumed.

## How a change lands

Every change, in every repository, lands through a pull request. `main` is
protected by a ruleset: it cannot be deleted or force-pushed, pull requests are
squash merged, and review threads must be resolved before merging.

Repository admins may bypass the review requirement **through a pull request** —
never by pushing to the branch. That exception exists for the release
workflows, which open and act on pull requests as `github-actions[bot]`.

Pull request titles follow [Conventional Commits][cc] and are checked. Because
pull requests are squash merged with the title as the commit subject, **the
title becomes the changelog entry**.

## Decisions that need writing down

Some things are too consequential to live only in a merged diff. These get a
numbered record under `docs/decisions/` in the repository they affect, and the
pull request links it:

- **anything that changes what people are paid** — the fee schedule, the
  attribution defaults, the split algorithm, the plan-id encoding;
- **anything that changes what a guarantee means** — the invariants, the
  verification methods, what a proof covers;
- **anything that gives the software a capability it deliberately lacks** —
  above all, holding a signing key.

`docs/settlement-architecture.md` in `dedalo` is the existing example, and it
is **binding**: if the code disagrees with it, one of the two is wrong, and the
answer is not to quietly change the code.

## Decisions that need more than one person

Today, none of these can happen, because there is one maintainer. That is the
point of listing them:

- **Funding a round.** Money moves from a multisig whose signers are not one
  person. Automation proposes; people sign. There is no key in CI and no
  configuration option that would put one there.
- **Deploying the claim contract**, which requires a published independent
  audit first.
- **Changing where the protocol fee goes.**

## The protocol fee

Every round a project settles routes `fees.protocol_bps` — 2.5% by default — to
the organisation's Open Collective at
[opencollective.com/dedalo](https://opencollective.com/dedalo). That is what
"the network funds itself" means.

Open Collective rather than a private account, because the ledger is public:
where the money went is a page anyone can read. **Nothing flows there yet** —
on-chain settlement is not live.

The default is a number in a config file that every adopting project can change
for itself, and changing the shipped default is a decision that needs a record
under the rules above.

## Disagreeing

In an issue or a [discussion][d], in public, before it is a branch. Cheaper to
reject a paragraph than a pull request.

Two things never go in public: anything where **an amount is or could be
wrong**, and anything from a wallet that signs. The first is a
[private advisory][sec] — that includes credit assigned to the wrong person,
because it is a payment defect. The second nobody will ever ask you for.

## Changing this document

A pull request against `dedalo-org/.github`. It is a default inherited by every
repository in the organisation, so a change here changes what all of them say.

[cc]: https://www.conventionalcommits.org
[d]: https://github.com/orgs/dedalo-org/discussions
[sec]: https://github.com/dedalo-org/.github/blob/main/SECURITY.md
