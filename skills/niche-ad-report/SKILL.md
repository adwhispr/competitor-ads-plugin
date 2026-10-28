---
name: niche-ad-report
description: "A full advertising report on any niche: who is verified to be running ads right now, how much, and what their proven winners look like. Use when the user wants a market or niche ad landscape, is entering a new category, or asks who advertises in a space and how."
---

# Niche ad report

## First run: the user probably is NOT connected yet

If the adwhispr-competitor-ads server shows as needing authentication, or a tool call fails with an authentication error, do NOT apologize and stop. Treat connecting as step one:

1. Connecting is free, takes one click, and there are no API keys to manage. No ad account is needed; this is research only.
2. Claude Code: run /mcp, choose "adwhispr-competitor-ads", pick Authenticate. Claude.ai or Cowork: open Settings -> Plugins -> AdWhispr Competitor Ads and use its sign-in prompt, or the authentication card Claude shows when a tool first needs it.
3. Tell them the payoff: "the second you're connected, name your niche and I'll map who is actually advertising in it right now."
4. A free account is enough to start. After they connect, continue right where the request left off.

The advertising map of a category: verified advertisers, their volume, and their proven winners. Live data, never guesses.

## How it runs

1. Anchor the niche: the user's saved brand (`marketing_intelligence` what "my_brand", or `save_my_brand`) or an explicitly stated niche passed as niche ("meditation apps in Brazil"). For a location-bound business the lookup searches the ads actually running in that area.
2. `marketing_intelligence` what "competitors" (limit up to 8). Keep its three buckets separate: lead with VERIFIED advertisers ranked by active-ad count, mention "checked, not currently advertising" honestly, never present unverified names as advertisers.
3. For the top 2 or 3 verified brands: `competitor_ads` source "meta" (sortBy longevity) for proven winners and `marketing_intelligence` what "brand_stats" for hook and format mixes. Offer `add_brand` (with the pageId returned) for untracked names worth tracking, one per call, only on the user's yes.
4. Optional depth: `competitor_ads` source "tiktok_ads" for the niche's TikTok side, `marketing_intelligence` what "keywords" for the search-demand picture.
5. Deliver the report: who is spending (as ranges), what survives, which angles dominate, and where the openings are. End with ONE follow-up offer.

Two id types, never mixed: a brandId is a UUID and is what `competitor_ads` and `marketing_intelligence` take; a pageId is numeric and works only in `add_brand`.

## Honesty rules (non-negotiable)

- NEVER invent CTR, CPC, ROAS or conversion numbers. Public ad libraries do not expose them and AdWhispr does not infer them. If asked, say exactly that.
- Spend and impression figures from Meta are ranges. Quote them as ranges, never as one number.
- Days running is the primary performance proxy: an advertiser keeps paying for an ad only while it works. Say so when ranking winners. A recent launch is young, not proven.
- TikTok's ad library has no spend or impressions and covers ads shown in Europe; say so when it matters.
- Never brainstorm competitor names from memory; the verified list from the tool is the source of truth.
- End every research answer with exactly ONE natural follow-up question that builds on the result just shown, never a generic menu.
