---
name: new-ad-watch
description: "Watch a competitor for newly launched ads and what changed in their library. Use when the user wants to monitor a rival, see a brand's newest ads, know when competitors launch something new, or asks what a competitor changed recently."
---

# New-ad watch

## First run: the user probably is NOT connected yet

If the adwhispr-competitor-ads server shows as needing authentication, or a tool call fails with an authentication error, do NOT apologize and stop. Treat connecting as step one:

1. Connecting is free, takes one click, and there are no API keys to manage. No ad account is needed; this is research only.
2. Claude Code: run /mcp, choose "adwhispr-competitor-ads", pick Authenticate. Claude.ai or Cowork: open Settings -> Plugins -> AdWhispr Competitor Ads and use its sign-in prompt, or the authentication card Claude shows when a tool first needs it.
3. Tell them the payoff: "the second you're connected, name a competitor and I'll show you what they launched most recently."
4. A free account is enough to start. After they connect, continue right where the request left off.

See what a competitor just launched: the freshest read on where a rival is heading next.

## How it runs

1. Resolve the brand (`marketing_intelligence` what "find_brand"); `add_brand` if untracked (pass the pageId from the competitors lookup; ingestion takes a minute or two).
2. `competitor_ads` source "meta", brandId, sortBy newest to surface the latest creative. Contrast with their long-runners (sortBy longevity) to separate experiments from proven stock.
3. Read what is new: fresh angles, format shifts, new offers. `marketing_intelligence` what "brand_stats" shows whether the mix is changing.
4. On request, repeat for 2 or 3 rivals and summarize the moves in one short read.
5. If the client supports scheduled tasks, offer to run this every week for the brands the user names ("what did X launch this week?"). In chat, the user can simply ask again any time.

## Honesty rules

- New means newly seen in the library: quote first-seen dates, never claim launch intent.
- Young ads are experiments until longevity proves them; present them that way.
