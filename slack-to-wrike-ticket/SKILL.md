---
description: "Create a Wrike ticket from a Slack thread, using only that thread's messages as context, then post a confirmation reply in the thread. Triggers: user pastes a Slack thread/message link and asks for a ticket, says 'create a ticket for this thread', 'raise a Wrike ticket from this conversation', 'ticket this', asks to scan a channel for flagged threads, or mentions a thread flagged with the :wrike-ticket: emoji."
---

# Slack to Wrike Ticket

Turn Slack threads into Wrike tasks without leaving the conversation.

## Quick Start

Paste a Slack thread link or channel name and ask to create a ticket. The skill reads the thread, builds a Wrike task with all relevant context, posts a confirmation in Slack, and gives you the Wrike link.

## What This Does

- **From a Slack link**: Create one Wrike ticket using only that thread's messages
- **From a channel name**: Scan for threads flagged with :wrike-ticket: and create tickets for each
- **Deduplication**: Skip threads that already have tickets (checks for existing Wrike links)
- **Confirmation**: Post a confirmation message in Slack for visibility and record-keeping

## How to Use

### Create a Ticket from a Thread

Share a Slack thread link:

```
https://blue-core.slack.com/archives/C0990L1N3AL/p1783696367706509
```

Then ask: "Create a Wrike ticket for this" or "Ticket this thread"

### Scan a Channel for Flagged Threads

Ask: "Check #production_leads for threads to ticket" or "Scan #channel-name for :wrike-ticket: reactions"

The skill will find all messages in that channel with the :wrike-ticket: emoji and create a ticket for each one.

## Configuration

Default settings (you can override these):

- **Destination folder**: "a) New Form Submissions" under Campaign Services Space (can be customized)
- **Scan channel**: #production_leads (or specify a different channel)
- **Trigger emoji**: :wrike-ticket: (custom Slack emoji)

## What You Get

The ticket includes:

- **Title**: Concise summary of the request (under 12 words)
- **Description**: Full context from the thread, structured with Summary, Key Details, Requested By, and Source
- **Importance**: Automatically set to High for urgent issues (outages, same-day deadlines)
- **Confirmation**: A reply in the Slack thread with the Wrike link and a request to verify the ticket

## Important Notes

- **Ticket description is built from the thread only** - pulling in context from other threads or channels produces confusing descriptions
- **One ticket per thread** - the skill deduplicates, so running it twice on the same thread won't create duplicates
- **No partial content** - if Wrike creation fails, the Slack confirmation is not posted (confirmation doubles as the deduplication marker)

## Error Handling

- If Wrike creation fails, the skill reports the error instead of posting to Slack
- If the user asks for a "dry run", the skill previews the title and description without creating anything
- Existing tickets are automatically skipped (detected by Wrike permalink in thread)

## Reference

For advanced configuration like custom Wrike folders, custom channels, or workflow customization, see the references folder.
