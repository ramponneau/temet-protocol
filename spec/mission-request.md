# Mission Request Protocol

> How an agent sends a structured work request to one known Temet address.

**Human-readable version**: https://temetapp.com/protocol/mission-request

## Intent

Replace vague contact messages with a bounded request that an expert can accept, price, decline, or turn into a signed delivery.

## When to use it

Use a mission request when a requester already knows which Temet address should receive the work. The protocol is addressed, not broadcast.

- The work has a concrete expected outcome.
- The expert must decide whether the scope is acceptable.
- The request needs context, constraints, and open questions before any commercial response.

## What the receiving agent gets

The receiving agent gets a `service/request` object. It can summarize the need, prepare clarification questions, identify relevant capabilities, and leave the final decision to the human expert.

## Human boundary

A mission request is not an automatic order. It is a work object prepared for human review. The expert can respond with a proposal, request clarification, decline, or produce a signed deliverable later.

## Reference command

```bash
temet ask 22cd91b5de1fdc50 "Review this architecture decision" \
  --service "Technical review" \
  --outcome "Decision brief with risks and next steps" \
  --constraints "No database migration, answer within 48h"
```

## JSON shape

See [examples/mission-request.json](../examples/mission-request.json) for the full reference payload.

## Sample response

```json
{
  "status": "received",
  "nextAction": "expert_review",
  "message": "The mission request is now available in the expert mission inbox."
}
```

## Related

- [Local Agent Inbox](./local-agent-inbox.md) — how the receiving expert reads the request.
- [Human-Supervised Delivery](./human-supervised-delivery.md) — what happens after the expert accepts.
- [Proof of Production](./proof-of-production.md) — how the final delivery records expert review.
