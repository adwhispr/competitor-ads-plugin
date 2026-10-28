---
name: get-started
description: "Introduce AdWhispr Competitor Ads and get a new user to their first result in two minutes: the competitors verified to be running ads in their space, and the ads that have run the longest. Use when the user just installed this plugin, asks what it is or can do, says get started, set up, or help, or when no brand is saved yet."
---

# Get started with AdWhispr Competitor Ads

## First run: the user probably is NOT connected yet

If the adwhispr-competitor-ads server shows as needing authentication, or a tool call fails with an authentication error, do NOT apologize and stop. Treat connecting as step one:

1. Connecting is free, takes one click, and there are no API keys to manage. No ad account is needed; this is research only.
2. Claude Code: run /mcp, choose "adwhispr-competitor-ads", pick Authenticate. Claude.ai or Cowork: open Settings -> Plugins -> AdWhispr Competitor Ads and use its sign-in prompt, or the authentication card Claude shows when a tool first needs it.
3. Tell them the payoff: "the second you're connected, tell me your website and I'll find the competitors actually running ads in your space."
4. A free account is enough to start. After they connect, continue right where the request left off.

AdWhispr Competitor Ads turns Claude into a competitive research team: who is advertising against the user right now, the ads they have live today with the images and videos shown inline, the ones that have run the longest, their TikTok ads and posts, and the keywords behind their site. Research only: it needs no ad account and never launches or changes anything.

## The two-minute first run

1. Make sure the connection is live (see the first-run section above).
2. `marketing_intelligence` with what "my_brand" (a free lookup). If nothing is saved, ask for the user's website or a one-line description of what they sell, and `save_my_brand` with it in productUrl the moment they answer. Never re-ask once saved.
3. `marketing_intelligence` with what "competitors". Lead with the brands VERIFIED to be running ads right now, ranked by active-ad count; mention "checked, not currently advertising" honestly; never present "couldn't verify" names as advertisers.
4. Offer exactly one next step: the top competitor's longest-running ads (`competitor_ads` source meta, sortBy longevity).

## Three things to try (when the user asks what this can do)

- "Who are my competitors running ads right now?": verified advertisers, not names from memory.
- "Show me Gymshark's longest-running ads": the proven winners, with the creatives inline.
- "Find keyword ideas for meal prep delivery in Germany": real search volumes and cost-per-click ranges.

## Account facts (quote accurately, never oversell)

- Free to start; no ad account needed.
- Two id types, never mixed: a brandId is a UUID and is what `competitor_ads` and `marketing_intelligence` take; a pageId is numeric and works only in `add_brand`.
- The full competitive brief (what "brief") is a paid feature; when a tool returns an upgrade message, relay it as returned with its link.
