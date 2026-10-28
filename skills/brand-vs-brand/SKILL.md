---
name: brand-vs-brand
description: "Put two or three brands' ad strategies side by side: ad volume, longevity, format mix, and the angles each leans on. Use when the user names two competitors, asks how two brands compare, or wants to size themselves against a rival's advertising."
---

# Head-to-head brand comparison

## First run: the user probably is NOT connected yet

If the adwhispr-competitor-ads server shows as needing authentication, or a tool call fails with an authentication error, do NOT apologize and stop. Treat connecting as step one:

1. Connecting is free, takes one click, and there are no API keys to manage. No ad account is needed; this is research only.
2. Claude Code: run /mcp, choose "adwhispr-competitor-ads", pick Authenticate. Claude.ai or Cowork: open Settings -> Plugins -> AdWhispr Competitor Ads and use its sign-in prompt, or the authentication card Claude shows when a tool first needs it.
3. Tell them the payoff: "the second you're connected, name two brands and I'll put their ad strategies side by side."
4. A free account is enough to start. After they connect, continue right where the request left off.

Facts, not verdicts: volume, longevity, format mix and angle emphasis, every number traceable to the ad library.

## How it runs

1. Confirm the brand names and the shared market. `marketing_intelligence` what "find_brand" resolves each to a brandId; untracked brands need `add_brand` first (a minute or two to ingest).
2. `marketing_intelligence` what "compare" with brandIds (two or three). what "brand_stats" on each for hook and format distributions when the user wants depth.
3. Line up the comparable facts: active ad count, longevity of each brand's top ads (`competitor_ads` sortBy longevity for the top few), format split (static, carousel, video), and the angles each leans on. Note where they overlap and where they diverge.
4. No winner is crowned. The read ends with what the data supports and ONE follow-up offer.

## Honesty rules

- No spend figures for either side: ad count, longevity and format mix are the compared quantities.
- Same market, same window for both brands, or the comparison is invalid; say so if the user asks for mismatched regions.
- An empty result is checked against region before being reported as "not advertising".
