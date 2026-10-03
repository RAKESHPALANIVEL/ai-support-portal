# Vision Support – Customer Site + Support Team Portal

Three files, no build step: `index.html`, `styles.css`, `script.js`. Open `index.html` in a browser.

## Who can do what
- **Customers** (no login): open the site, fill in the form, optionally use **Analyze with AI**, submit, and get a ticket ID.
- **Support Team** (login with **Name + Email ID** only): click "Support Team Login" → dashboard, all tickets, ticket details, status updates, AI-suggested replies.

Demo login: any name + `support@visionsupport.com`.
Authorized emails are listed in the `SUPPORT_TEAM` array at the top of `script.js`.

## AI features
- Customer form: detects category and priority, writes a summary (built-in engine).
- Support dashboard: AI insights (top issue, critical tickets, frustrated customers, oldest unresolved ticket, resolution rate).
- Ticket details: AI summary, sentiment, editable suggested reply, one-click "Reply by email", re-analyze.
- Optional: add a Gemini API key under **AI settings** (support team only) to use Google Gemini for re-analysis.

## Important limitations (front-end only)
- Name + email login has no password, so it is only a gate based on the allow-list in `script.js`. Anyone who can read the source can see that list. For real security, verify users on a server.
- Tickets are stored in the browser's localStorage, so the support dashboard shows tickets submitted from the same browser. To share tickets across devices you need a backend/database.
