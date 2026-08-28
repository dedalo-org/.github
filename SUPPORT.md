# Support

Four questions, four places. This is an organisation-wide default, so it has to
be true of every repository here — including the ones that are not `dedalo`.

**"How does this work?"** — [the handbook][handbook]. It covers the pipeline,
what a round is, how attribution scores a merge, and what the guarantees mean.
Start with the [FAQ][faq] if the question is short.

**"How do I ask a question?"** — [discussions][discussions], which are
organisation-wide rather than per repository. A question that turns out to be a
documentation gap is treated as a bug in the documentation, and answering it
usually ends in a pull request to the handbook.

**"This is broken."** — an issue on the repository in question. Include the
version or commit, what you expected, and what happened. A reproduction is
worth more than a description.

**"I found a vulnerability."** — do not open an issue. Follow
[the security policy][security]. If the repository ships its own `SECURITY.md`,
read that one: it describes that project's threat model, and for `dedalo` a
wrong payout amount is a security issue rather than an ordinary bug.

**"I want to change something."** — [the contributing guide][contributing]
first. For anything larger than a fix, open an issue before writing the code so
the design can be agreed on. A rejected design is much cheaper as a paragraph
than as a finished branch.

## What to expect

These are volunteer-maintained projects. There is no support SLA, and the
fastest path to a fix is usually a pull request with a failing test.

[handbook]: https://dedalo-org.github.io/dedalo/
[faq]: https://dedalo-org.github.io/dedalo/faq.html
[discussions]: https://github.com/orgs/dedalo-org/discussions
[security]: https://github.com/dedalo-org/.github/blob/main/SECURITY.md
[contributing]: https://github.com/dedalo-org/.github/blob/main/CONTRIBUTING.md
