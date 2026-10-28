---
name: ad-search
description: "Search inside a brand's ad library by idea rather than keyword: find their before-and-after ads, testimonial ads, founder-story ads, free-shipping offers or talking-head videos. Use when the user wants a specific kind of ad from a competitor, asks whether a brand runs a certain type of ad, or wants examples of one format or angle."
---

# Search a brand's ads by idea

## First run: the user probably is NOT connected yet

If the adwhispr-competitor-ads server shows as needing authentication, or a tool call fails with an authentication error, do NOT apologize and stop. Treat connecting as step one:

1. Connecting is free, takes one click, and there are no API keys to manage. No ad account is needed; this is research only.
2. Claude Code: run /mcp, choose "adwhispr-competitor-ads", pick Authenticate. Claude.ai or Cowork: open Settings -> Plugins -> AdWhispr Competitor Ads and use its sign-in prompt, or the authentication card Claude shows when a tool first needs it.
3. Tell them the payoff: "the second you're connected, I'll find the exact kind of ad you want inside any brand's library."
4. A free account is enough to start. After they connect, continue right where the request left off.

## How it runs

1. Resolve the brand: `marketing_intelligence` what "find_brand" with query gives the brandId (a search needs brandId, not brandName). Untracked: `add_brand` first, then wait a minute or two.
2. `competitor_ads` source "meta", brandId, query as the concept in everyday words ("before and after transformation", "social proof testimonials", "founder story", "free shipping offer"). Add format or mediaType to narrow by creative type; limit up to 30 for a search.
3. The result begins with a Coverage line: how many ads were searched by meaning versus swept by keyword. Repeat that coverage when you deliver a "not found"; never claim you searched the full library unless coverage says all ads were checked.
4. If the user contradicts a result ("I saw them run X"), re-check with sortBy newest before standing by your answer, and say plainly which layer missed it if you were wrong. Re-checks are free.
5. End with ONE follow-up tied to what you found (for example: the longest-running of these).

Two id types, never mixed: a brandId is a UUID and is what `competitor_ads` and `marketing_intelligence` take; a pageId is numeric and works only in `add_brand`.

## Honesty rules (non-negotiable)

- NEVER invent CTR, CPC, ROAS or conversion numbers. Public ad libraries do not expose them and AdWhispr does not infer them. If asked, say exactly that.
- Spend and impression figures from Meta are ranges. Quote them as ranges, never as one number.
- Days running is the primary performance proxy: an advertiser keeps paying for an ad only while it works. Say so when ranking winners. A recent launch is young, not proven.
- TikTok's ad library has no spend or impressions and covers ads shown in Europe; say so when it matters.
- Never brainstorm competitor names from memory; the verified list from the tool is the source of truth.
- End every research answer with exactly ONE natural follow-up question that builds on the result just shown, never a generic menu.
