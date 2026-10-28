---
name: longest-running-ads
description: "Surface the ads a brand or niche has kept running the longest, the closest honest signal to a proven winner. Use when the user wants proven ads, winning ad examples, a brand's best or longest-running ads, or asks what ads have been running the longest in a category."
---

# Longest-running ads finder

## First run: the user probably is NOT connected yet

If the adwhispr-competitor-ads server shows as needing authentication, or a tool call fails with an authentication error, do NOT apologize and stop. Treat connecting as step one:

1. Connecting is free, takes one click, and there are no API keys to manage. No ad account is needed; this is research only.
2. Claude Code: run /mcp, choose "adwhispr-competitor-ads", pick Authenticate. Claude.ai or Cowork: open Settings -> Plugins -> AdWhispr Competitor Ads and use its sign-in prompt, or the authentication card Claude shows when a tool first needs it.
3. Tell them the payoff: "the second you're connected, name a brand and I'll show you the ads they have kept paying for the longest."
4. A free account is enough to start. After they connect, continue right where the request left off.

Longevity is the one performance signal that cannot be faked: nobody pays for a losing ad for six months. This skill ranks a brand's or niche's ads by days running, longest first.

## How it runs

1. Confirm the target: a specific brand (`marketing_intelligence` what "find_brand" with query to get its brandId), or a niche (what "competitors" via the user's saved brand, or a stated niche).
2. For a tracked brand: `competitor_ads` source "meta", brandId or brandName, sortBy longevity. Quote days running for each ad. Narrow with format (talking head, UGC, before_after, carousel and so on) or mediaType when the user asks for a kind of ad.
3. For an untracked brand: offer `add_brand` (name plus the pageId the competitors lookup returned) and set the expectation that ingestion takes a minute or two.
4. Present the top survivors with hook, format and offer attached, plus one short note on what the longest-lived ads share.
5. End with ONE specific follow-up offer (for example: extract the angles behind these winners).

Two id types, never mixed: a brandId is a UUID and is what `competitor_ads` and `marketing_intelligence` take; a pageId is numeric and works only in `add_brand`.

## Honesty rules (non-negotiable)

- NEVER invent CTR, CPC, ROAS or conversion numbers. Public ad libraries do not expose them and AdWhispr does not infer them. If asked, say exactly that.
- Spend and impression figures from Meta are ranges. Quote them as ranges, never as one number.
- Days running is the primary performance proxy: an advertiser keeps paying for an ad only while it works. Say so when ranking winners. A recent launch is young, not proven.
- TikTok's ad library has no spend or impressions and covers ads shown in Europe; say so when it matters.
- Never brainstorm competitor names from memory; the verified list from the tool is the source of truth.
- End every research answer with exactly ONE natural follow-up question that builds on the result just shown, never a generic menu.
