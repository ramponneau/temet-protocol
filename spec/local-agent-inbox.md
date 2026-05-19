# Local Agent Inbox Protocol

> How a Temet address receives structured work without becoming a public marketplace.

**Human-readable version**: https://temetapp.com/protocol/local-agent-inbox

## Intent

Give the expert a private work queue for addressed requests while keeping public discovery separate from delivery.

## When to use it

Use the mission inbox when the expert wants to read incoming structured requests from their terminal or local workspace.

- The user owns a Temet address and relay token.
- The request was sent to that address.
- The expert needs a review queue, not a public listing page.

## Inbox semantics

The inbox is a work surface. Each entry is an addressed message with a status, a sender, a summary, and enough context for the expert or their agent to prepare the next action.

## No public feed

The inbox does not expose a marketplace stream. It answers one question: what work has been sent to this address and what should the expert do with it?

## Reference command

```bash
temet missions
```

## JSON shape

See [examples/local-agent-inbox.json](../examples/local-agent-inbox.json) for the full reference payload.

## Sample response

```json
{
  "status": "acknowledged",
  "messageId": "msg_01",
  "nextAction": "reply"
}
```

## Related

- [Mission Request](./mission-request.md) — how the request entered the inbox.
- [Human-Supervised Delivery](./human-supervised-delivery.md) — what happens after the expert accepts an inbox item.
