---
description: "Quick partner account status from Wrike (campaign tasks, ownership, blockers, recent activity). Optionally includes Jira data. Triggers: 'status for [partner]', 'what's happening with [partner]', 'who owns [partner]', 'catch me up on [partner]', 'is [partner] blocked', 'what's the deal with [partner]'."
---

# Partner Intel

Get a quick status snapshot of any partner account. See their campaign tasks, who owns what, any blockers, and recent activity.

## Quick Start

Ask about any partner by name:
- "Status for Nike"
- "What's happening with GPUS"
- "Is Backcountry blocked"

The skill pulls their current campaign work from Wrike and shows you what's in flight, who owns it, and what's stuck.

## What You Get

By default, the skill shows:

- **Campaign tasks** - Open work items in Wrike for that partner
- **Ownership** - Who is assigned to each task
- **Blockers** - What's stuck or waiting
- **Recent activity** - Latest updates and status changes

All data comes from Wrike. If you need technical details about tickets or bugs, you can optionally ask for Jira data too.

## Options

### Include Jira Data

If a partner has open technical issues, ask for Jira details:
- "Status for [partner], including any Jira tickets"
- "What's the deal with [partner] - check both Wrike and Jira"

The skill will then pull both campaign status (Wrike) and technical issues (Jira).

### Just Wrike (Default)

Most queries default to Wrike only, which is usually what you need for quick status checks.

## How It Works

1. **Search by partner name** - Finds the account in Wrike
2. **Pull campaign data** - Shows open tasks, assignments, and status
3. **Identify blockers** - Flags tasks that are stuck or waiting
4. **Optional Jira lookup** - If you ask, also fetches related technical tickets

## Data Sources

- **Wrike** - Campaign tasks, ownership, due dates, blockers
- **Jira** (optional) - Technical issues, bug status, epic tracking

## Conciseness

This skill surfaces the most relevant items. If there are many open tasks, it highlights the key ones and acknowledges there's more available on request.

## Common Asks

- "Catch me up on Nike" → Shows their Wrike status
- "Is Backcountry blocked" → Flags any blockers
- "Who owns the Klaviyo integration for GPUS" → Shows specific task ownership
- "Status for Nike, include any open bugs" → Wrike + Jira view

## Limits

- **Numeric IDs** - Internally uses Wrike numeric IDs, but shows partner names in results
- **Verified data only** - Only uses confirmed partner accounts from Wrike
- **Recent activity** - Shows latest activity; older items are available if you ask
