# Proof of Supervision Protocol

> How a supervised delivery records human review, corrections, and a verifiable content hash.

**Human-readable version**: https://temetapp.com/protocol/proof-of-supervision

## Intent

Give clients evidence that a human expert reviewed the work before delivery.

## When to use it

Use proof of supervision when the final delivery must show that expert review happened before the output was sent.

- The client needs a defensible final deliverable.
- The expert made corrections or accepted responsibility for the result.
- The delivery should be verifiable later through a content hash or receipt.

## What is recorded

The protocol records the mission, the final deliverable hash, the review status, the expert identity, and the supervision evidence that can be shown to a client.

## What it does not prove

It does not claim the machine was always correct. It proves the delivery passed through a human supervision boundary before it was finalized.

## Reference command

```bash
temet mission <mission_id> close --deliverable ./delivery.md
```

## JSON shape

See [examples/proof-of-supervision.json](../examples/proof-of-supervision.json) for the full reference payload.

## Sample response

```json
{
  "status": "delivered",
  "receipt": {
    "id": "rcpt_01",
    "hash": "receipt_hash",
    "prevHash": "previous_receipt_hash"
  }
}
```

## Related

- [Human-Supervised Delivery](./human-supervised-delivery.md) — the step that produces the deliverable.
- [Mission Request](./mission-request.md) — the original addressed request.
