# Auth & Logic Flaws (Class 3)

## Patterns
- Response tampering: { "success": false } -> true
- Status code ignore: 403 response but action still applied
- Mass assignment: POST extra param (is_admin:true, role:admin)
- Race condition: fire 10 parallel requests (coupon, balance, invite)
- Password reset: token not consumed / predictable / emailed to attacker-controlled
- OAuth: redirect_uri allowlist bypass, state missing -> CSRF login
- 2FA: can reach /account after "skip" or by reusing session

## How to test
- Intercept EVERY response. Don't trust client-side state.
- Look for "privileged" params in forms (disable hidden fields, add role=).
- Race: use turbo intruder / parallel curl.

## Mindmap
Logic bugs live where the DEV assumed the client behaves. Break the assumption.
