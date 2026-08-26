# Payment & Checkout Logic (Class 4 — Stripe scope)

## Patterns (test-mode only, then report)
- Amount override: negative qty, 0 amount, currency swap
- Coupon/promo stacking beyond limit
- Payment Link param tampering: prefilled_email, quantity, price id
- Connect: Stripe-Account header cross-account access
- Race on checkout completion (double fulfill)
- Webhook replay: replay checkout.session.completed with forged ID

## Mindmap
Money flows are STATE MACHINES. Every transition (cart->pay->fulfill) is a
boundary. Ask: can I replay, skip, or reverse a transition? Test-mode first.
