# SSRF (Class 2)

## What it is
Server fetches a URL YOU control. Chain it to reach internal/cloud metadata.

## Where to look
- Webhook URL config
- Image/file import by URL (?url=, avatar upload by link)
- PDF generators that fetch HTML
- Integration callbacks (Slack, Slack-like)
- "Test connection" buttons in dashboards

## How to test
1. Point the URL at an interactsh/oast.me domain you control.
2. Confirm the server hits it (DNS + HTTP).
3. Try internal: http://169.254.169.254/ (cloud metadata), http://localhost:port
4. Bypass filters: redirects, decimal IP, [::], 0.0.0.0

## Mindmap
SSRF = the server is a proxy you command. Every "fetch by URL" feature is a
candidate. Blind SSRF = only DNS hits (use oast.me).
