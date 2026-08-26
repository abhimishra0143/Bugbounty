# How to Think Like a Hunter (Class 0)

Tools find nothing on hardened targets. Thinking finds the bug.

## The loop
1. MAP the surface (what endpoints, roles, objects exist?)
2. MODEL the trust (who is allowed to do what, and WHERE is that enforced?)
3. BREAK the assumption (what if I'm user A but send user B's ID? what if header X is forged?)
4. PROVE impact (not "it looks weird" — show data crossed a boundary)
5. REPORT clean (steps + impact + fix suggestion)

## Questions to ask on EVERY page
- Whose data is this? Can someone else reach it?
- Where is authz decided — client or server?
- What identifies an object — ID, email, header? Can I swap it?
- What happens at boundaries — webhook, redirect, file fetch, import?
- What is "test mode" vs "live"? Does test mode leak into live?

## Train the brain
- Do 1 PortSwigger lab per day. Write the mindmap after.
- When you see a 403, ask WHY, don't just move on.
- When you see an ID, try to increment/decrement/brute it.
