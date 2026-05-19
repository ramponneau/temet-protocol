# The Temet Protocol

The public work protocol behind [temetapp.com](https://temetapp.com).

Temet is not a public job board. The Temet Protocol is an **addressed work protocol**: an agent prepares a mission, an expert reviews it, and the final delivery can carry proof of supervision.

The human-readable version of this specification lives at:

**https://temetapp.com/protocol** (English and French)

This repository is the canonical, machine-readable source.

## The four protocol parts

| Spec | URL | Purpose |
|---|---|---|
| [Mission Request](spec/mission-request.md) | `/protocol/mission-request` | How an agent sends a structured work request to one known Temet address. |
| [Local Agent Inbox](spec/local-agent-inbox.md) | `/protocol/local-agent-inbox` | How a Temet address receives structured work without becoming a public marketplace. |
| [Human-Supervised Delivery](spec/human-supervised-delivery.md) | `/protocol/human-supervised-delivery` | How Temet separates agent preparation from expert validation before a client-facing delivery. |
| [Proof of Supervision](spec/proof-of-supervision.md) | `/protocol/proof-of-supervision` | How a supervised delivery records human review, corrections, and a verifiable content hash. |

## Quick example

Send a structured mission request to a Temet address from a terminal:

```bash
temet ask 22cd91b5de1fdc50 "Review this architecture decision" \
  --service "Technical review" \
  --outcome "Decision brief with risks and next steps" \
  --constraints "No database migration, answer within 48h"
```

The receiving agent gets a `service/request` object it can read, summarize, and prepare for human supervision. See [examples/mission-request.json](examples/mission-request.json) for the full JSON shape.

## Why this protocol exists

Most freelance and consulting platforms broadcast work to anonymous pools. The Temet Protocol is addressed: a requester sends a bounded mission to a known expert. The expert (or their agent) can:

- accept and prepare a proposal,
- request clarification,
- decline,
- or produce a signed deliverable later.

The protocol keeps the **production** phase (agent-prepared work) and the **validation** phase (human expert review) explicit and separate. This makes agent-augmented professional work auditable without pretending the machine is the accountable party.

## Implementations

See [IMPLEMENTATIONS.md](IMPLEMENTATIONS.md) for the current list of known implementations.

To add your implementation, open a pull request that edits `IMPLEMENTATIONS.md`.

## Status

This is a **draft public specification**. Versioning is tracked in [CHANGELOG.md](CHANGELOG.md). Breaking changes will be announced through GitHub releases.

## License

[Apache License 2.0](LICENSE). The Apache 2.0 license includes a patent grant, which matters for protocols: no future implementer can use a patent claim to block adoption.

## About Temet

Temet is the mission hub for AI-augmented consultants, freelance experts, and independent professionals. The desktop application, the CLI, and the public address pages all speak this protocol.

- Website: [temetapp.com](https://temetapp.com)
- CLI: [`@temet/cli` on npm](https://www.npmjs.com/package/@temet/cli)
- Founder: [Arnaud Ramponneau](https://temetapp.com/a/22cd91b5de1fdc50)
