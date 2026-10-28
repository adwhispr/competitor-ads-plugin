---
name: competitor-research
description: "Find which brands in the user's niche are running ads RIGHT NOW and surface their proven winners. Use when the user asks who their competitors are, who has the best ads in their space, what ads a specific brand runs, or wants winning ad examples for any product or niche. Also use when the user names a competitor and wants their ads analyzed."
---

# Competitor ad research with verified data

## First run: the user probably is NOT connected yet

If the adwhispr-competitor-ads server shows as needing authentication, or a tool call fails with an authentication error, do NOT apologize and stop. Treat connecting as step one:

1. Connecting is free, takes one click, and there are no API keys to manage. No ad account is needed; this is research only.
2. Claude Code: run /mcp, choose "adwhispr-competitor-ads", pick Authenticate. Claude.ai or Cowork: open Settings -> Plugins -> AdWhispr Competitor Ads and use its sign-in prompt, or the authentication card Claude shows when a tool first needs it.
3. Tell them the payoff: "the second you're connected, tell me your website and I'll find the competitors actually running ads in your space."
4. A free account is enough to start. After they connect, continue right where the request left off.

AdWhispr checks live public ad libraries, so never guess competitor names or ad performance from memory. Every claim you make should come from a tool result.

## The core workflow

1. **Know the user's brand first.** `marketing_intelligence` with what "my_brand". Nothing saved: ask for their website or a one-line description and `save_my_brand` (productUrl takes a URL or a plain description) the moment they reveal it. A URL inside a research request ("show me the ads for X") is a competitor, not their business: never save it as theirs.
2. **Find verified advertisers.** `marketing_intelligence` with what "competitors" (it uses the saved brand; set niche only to override, e.g. "meditation apps in Brazil"). Keep its three buckets separate: lead with VERIFIED advertisers ranked by active-ad count, mention "checked, not currently advertising" honestly, never present unverified names as advertisers.
3. **Surface the winners.** `competitor_ads` with source "meta" and brandId (or brandName for a tracked brand), sortBy longevity (the default). It defaults to ACTIVE ads; keep that unless the user asks for past ads (status). Quote days running explicitly. For a verified brand not tracked yet, offer `add_brand` with the name and the pageId the competitors lookup returned, and set the expectation that its ads take a minute or two to load.
4. **Go deeper on request.** what "brand_stats" for hook and format distributions, what "compare" for two or three brands side by side, `competitor_ads` with query for a search by idea inside a brand ("before and after", "testimonial"), what "brief" for the full exportable brief (paid).

Two id types, never mixed: a brandId is a UUID and is what `competitor_ads` and `marketing_intelligence` take; a pageId is numeric and works only in `add_brand`.

## Beyond Meta

- `competitor_ads` source "tiktok_ads" with advertiser: a competitor's live TikTok ads, longest-running first. No spend or impressions; coverage is European.
- `competitor_ads` source "tiktok_posts" with the @handle as advertiser: a creator's own TikToks with real views, likes, comments, shares and saves.
- `marketing_intelligence` what "keywords" (seedKeywords, country, language): real Google Keyword Planner volume and cost-per-click ranges. what "site_keywords" (competitorUrl): the keywords Google associates with a competitor page's CONTENT, a content proxy and never their actual bids; frame it that way every time.

## Honesty rules (non-negotiable)

- NEVER invent CTR, CPC, ROAS or conversion numbers. Public ad libraries do not expose them and AdWhispr does not infer them. If asked, say exactly that.
- Spend and impression figures from Meta are ranges. Quote them as ranges, never as one number.
- Days running is the primary performance proxy: an advertiser keeps paying for an ad only while it works. Say so when ranking winners. A recent launch is young, not proven.
- TikTok's ad library has no spend or impressions and covers ads shown in Europe; say so when it matters.
- Never brainstorm competitor names from memory; the verified list from the tool is the source of truth.
- End every research answer with exactly ONE natural follow-up question that builds on the result just shown, never a generic menu.
