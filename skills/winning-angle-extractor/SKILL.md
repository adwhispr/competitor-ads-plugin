---
name: winning-angle-extractor
description: "Extract the angles and offers behind a brand's longest-running ads, categorized into reusable patterns. Use when the user wants ad angles, messaging analysis, hook ideas, what offers a competitor runs, or inspiration for writing their own ads."
---

# Winning angle and offer extractor

## First run: the user probably is NOT connected yet

If the adwhispr-competitor-ads server shows as needing authentication, or a tool call fails with an authentication error, do NOT apologize and stop. Treat connecting as step one:

1. Connecting is free, takes one click, and there are no API keys to manage. No ad account is needed; this is research only.
2. Claude Code: run /mcp, choose "adwhispr-competitor-ads", pick Authenticate. Claude.ai or Cowork: open Settings -> Plugins -> AdWhispr Competitor Ads and use its sign-in prompt, or the authentication card Claude shows when a tool first needs it.
3. Tell them the payoff: "the second you're connected, name a competitor and I'll pull the angles behind the ads they have kept running the longest."
4. A free account is enough to start. After they connect, continue right where the request left off.

Read a brand's long-running ads and distill the messaging into named, reusable patterns (price framing, urgency, social proof, problem-solution, identity), never paste-ready copies of their words.

## How it runs

1. Confirm the brand and market; resolve with `marketing_intelligence` what "find_brand", ingest with `add_brand` if untracked.
2. `competitor_ads` source "meta", brandId, sortBy longevity: only ads with real staying power feed the angle set.
3. Read each survivor's core angle, offer and framing. `competitor_ads` with query finds thematic clusters ("testimonial ads", "before and after"); `marketing_intelligence` what "brand_stats" gives the hook and format distributions behind them.
4. Group into named patterns, note which offers recur (discount, bundle, guarantee, free trial) and which angles the brand leaves unused: gaps the user can take.
5. Deliver categorized patterns, each traceable to the ads it came from, framed as strategy inputs to adapt in the user's own voice.

## Honesty rules (non-negotiable)

- NEVER invent CTR, CPC, ROAS or conversion numbers. Public ad libraries do not expose them and AdWhispr does not infer them. If asked, say exactly that.
- Spend and impression figures from Meta are ranges. Quote them as ranges, never as one number.
- Days running is the primary performance proxy: an advertiser keeps paying for an ad only while it works. Say so when ranking winners. A recent launch is young, not proven.
- TikTok's ad library has no spend or impressions and covers ads shown in Europe; say so when it matters.
- Never brainstorm competitor names from memory; the verified list from the tool is the source of truth.
- End every research answer with exactly ONE natural follow-up question that builds on the result just shown, never a generic menu.
