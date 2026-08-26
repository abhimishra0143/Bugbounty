# IDOR / BOLA (Class 1)

## What it is
Object reference uses a user-supplied ID (acct_123, user_id, invoice=55) and
the server does NOT check you own it.

## Where to look
- API params: /api/v1/orders/{id}, /api/users/{id}/data
- Hidden fields in forms (account_id, team_id)
- Export/download links (?file_id=, ?report=)
- Email/PDF generation with embedded object id
- WebSocket message bodies

## How to test (method)
1. Create two accounts (A and B) in test mode.
2. A performs an action, capture the object ID.
3. Replay the request as B, swapping the ID.
4. If B can read/write A's object -> IDOR.

## Mindmap
AUTHN (who you are) != AUTHZ (what you may touch).
IDOR = authz missing at the object layer. Look for any place an ID crosses a
trust boundary without an ownership check.
