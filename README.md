# The Cleaners Place for Claude and ChatGPT

Run your cleaning business by chatting. Owners, managers and cleaners connect their own account and can do what their role can already do in The Cleaners Place. Anything that spends money, emails a customer, or deletes data asks for confirmation first.

## Before you install

The account **owner** turns on AI access once: in The Cleaners Place, open **AI assistant** in the dashboard and click **Turn on AI access**. After that anyone on the team can connect.

## Install in Claude (Claude Code or Claude desktop with plugins)

```
/plugin marketplace add alexlovelady/the-cleaners-place-ai
/plugin install the-cleaners-place@the-cleaners-place
```

Then run any workflow, for example "good morning" or "plan my week". The first use opens a sign-in window.

Prefer not to use plugins? Add the connector directly: Claude, Settings, Connectors, Add custom connector, URL `https://thecleanersplace.com/mcp`.

## Install in the ChatGPT desktop app

```
codex plugin marketplace add alexlovelady/the-cleaners-place-ai
```

Restart the app, open Plugins, install **The Cleaners Place**. Installing only adds it: then open the **MCPs** tab in Plugins, find **The Cleaners Place** and click **Authenticate** (sign in and allow access). Direct route: Settings, Plugins, Add, Add MCP server, Streamable HTTP, URL `https://thecleanersplace.com/mcp`.

## What is inside

`plugins/the-cleaners-place/` holds the connection config for both apps and ready-made workflows (skills):

| Skill | For | What it does |
| --- | --- | --- |
| setup | everyone | explains what you can do, the safety rules, and how to reach support |
| morning-briefing | owner / manager | today's jobs, what needs attention, money due |
| end-of-day-wrap-up | owner / manager | unfinished jobs, clock times, tomorrow's schedule |
| plan-my-week | owner / manager | fix double bookings, assign, reschedule, route order |
| chase-overdue-invoices | owner / manager | collect what is owed, one confirmed step at a time |
| quote-followup | owner / manager | chase unanswered quotes, book or close them |
| new-customer | owner / manager | customer, property, quote or booking, recurring service |
| reactivate-lapsed-customers | owner / manager | find customers who stopped booking and win them back |
| weekly-review-run | owner / manager | ask recent customers for reviews, one by one |
| recurring-schedule-health-check | owner / manager | crews, holds and gaps on repeat customers |
| handle-incident-or-complaint | owner / manager | from first report to resolution, refunds go to support |
| hire-and-onboard-cleaner | owner / manager | invite, onboarding checklist, documents, pay, first jobs |
| time-off-requests | owner / manager | decide requests with schedule impact |
| team-and-keys-audit | owner / manager | expiring documents, onboarding gaps, key access |
| supply-restock | owner / manager | what is low, record the purchase |
| pay-day | owner / manager | review, finalize and pay a pay run |
| month-end-review | owner / manager | revenue, profit, expenses, receivables |
| tax-season-prep | owner / manager | totals and missing items for your accountant |
| my-day | cleaner | today's jobs, route, check in/out, notes, complete a job |
| my-pay-and-time-off | cleaner | pay status, expenses, time off, report a pay problem |

## Safety

The assistant acts as you, with your role's permissions only. Disconnect any app any time from the AI assistant page in the dashboard. Every action it takes is logged there.
