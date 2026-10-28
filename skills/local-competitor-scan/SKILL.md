---
name: local-competitor-scan
description: "Find who is advertising in a specific city, region or country for a local service or store, and what their ads look like. Use when the user runs a location-bound business (dentist, salon, gym, restaurant, clinic, contractor, real estate) and asks who their local competitors are or what ads run in their area."
---

# Local competitor scan

## First run: the user probably is NOT connected yet

If the adwhispr-competitor-ads server shows as needing authentication, or a tool call fails with an authentication error, do NOT apologize and stop. Treat connecting as step one:

1. Connecting is free, takes one click, and there are no API keys to manage. No ad account is needed; this is research only.
2. Claude Code: run /mcp, choose "adwhispr-competitor-ads", pick Authenticate. Claude.ai or Cowork: open Settings -> Plugins -> AdWhispr Competitor Ads and use its sign-in prompt, or the authentication card Claude shows when a tool first needs it.
3. Tell them the payoff: "the second you're connected, tell me your service and your city and I'll show you who is advertising there right now."
4. A free account is enough to start. After they connect, continue right where the request left off.

For a location-bound business, the competitors that matter are the ones advertising in the same area. The competitors lookup searches the ads actually running there.

## How it runs

1. `marketing_intelligence` what "my_brand"; if nothing is saved, ask for the website or one line with the service and the place, and `save_my_brand` it. If the user states the area in the request, put it in niche ("dentists in Austin", "yoga studios in Lisbon").
2. `marketing_intelligence` what "competitors". Lead with the VERIFIED advertisers in that area ranked by active-ad count; keep the other two buckets separate and honest.
3. For the top 2 or 3: `competitor_ads` source "meta", sortBy longevity, to see the offers and hooks that have survived months of local spend (free consultation, first-visit discount, before-and-after, reviews). Offer `add_brand` (with the pageId returned) for an untracked local rival, one per call.
4. Deliver: who advertises locally, what offers they lead with, how long their best ads have run, and the angle nobody in the area is using.
5. End with ONE follow-up tied to the result.

Two id types, never mixed: a brandId is a UUID and is what `competitor_ads` and `marketing_intelligence` take; a pageId is numeric and works only in `add_brand`.

## Honesty rules (non-negotiable)

- NEVER invent CTR, CPC, ROAS or conversion numbers. Public ad libraries do not expose them and AdWhispr does not infer them. If asked, say exactly that.
- Spend and impression figures from Meta are ranges. Quote them as ranges, never as one number.
- Days running is the primary performance proxy: an advertiser keeps paying for an ad only while it works. Say so when ranking winners. A recent launch is young, not proven.
- TikTok's ad library has no spend or impressions and covers ads shown in Europe; say so when it matters.
- Never brainstorm competitor names from memory; the verified list from the tool is the source of truth.
- End every research answer with exactly ONE natural follow-up question that builds on the result just shown, never a generic menu.
