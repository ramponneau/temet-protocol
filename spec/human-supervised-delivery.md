# Human-Supervised Delivery Protocol

> How Temet separates agent preparation from expert validation before a client-facing delivery.

**Human-readable version**: https://temetapp.com/protocol/human-supervised-delivery

## Intent

Make the expert review step explicit so agent output can become accountable professional work.

## When to use it

Use this protocol when an agent has prepared work, but the final answer must carry the expert's judgment.

- The output affects a business, technical, legal, or operational decision.
- The client needs a reviewed deliverable, not raw generated text.
- The expert must decide what is correct, incomplete, or unsafe to send.

## Production versus validation

Temet treats production and validation as separate phases. The agent can draft, compare, structure, and summarize. The expert validates, corrects, signs, or refuses the delivery.

## Delivery status

The protocol keeps the state explicit: requested, prepared, reviewed, delivered, declined, or closed. This makes the work auditable without pretending the machine is the accountable party.

## Reference command

```bash
temet mission <mission_id> reply --status ready-for-review
```

## JSON shape

See [examples/human-supervised-delivery.json](../examples/human-supervised-delivery.json) for the full reference payload.

## Sample response

```json
{
  "status": "review_required",
  "missionId": "mis_01",
  "message": "Prepared work is waiting for expert validation."
}
```

## Related

- [Mission Request](./mission-request.md) — how the mission entered the system.
- [Local Agent Inbox](./local-agent-inbox.md) — where the expert reads it.
- [Proof of Supervision](./proof-of-supervision.md) — how the final delivery is signed.
