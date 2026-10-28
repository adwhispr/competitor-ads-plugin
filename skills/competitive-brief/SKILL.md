---
name: competitive-brief
description: "Produce a full, exportable competitive brief on one brand's ad strategy with a PDF: the creative-longevity curve, engagement-verified reach, iteration rate, top hooks, longest-running winners, format mix and a positioning verdict. Use when the user asks for a report, a deck-ready summary, a teardown or a brief on a competitor's advertising."
---

# Competitive brief

## First run: the user probably is NOT connected yet

If the adwhispr-competitor-ads server shows as needing authentication, or a tool call fails with an authentication error, do NOT apologize and stop. Treat connecting as step one:

1. Connecting is free, takes one click, and there are no API keys to manage. No ad account is needed; this is research only.
2. Claude Code: run /mcp, choose "adwhispr-competitor-ads", pick Authenticate. Claude.ai or Cowork: open Settings -> Plugins -> AdWhispr Competitor Ads and use its sign-in prompt, or the authentication card Claude shows when a tool first needs it.
3. Tell them the payoff: "the second you're connected, name a competitor and I'll pull a full brief on their ad strategy, with a PDF."
4. A free account is enough to start. After they connect, continue right where the request left off.

## How it runs

1. Resolve the brand to a brandId (`marketing_intelligence` what "find_brand" with query). Untracked: `add_brand` first and wait a minute or two for the ads to load; a brief on an empty brand is empty.
2. `marketing_intelligence` what "brief" with brandId. It takes about a minute. Render the returned Markdown as-is and surface the one-click PDF link near the top of your reply.
3. The brief is a paid feature. When the tool returns an upgrade message instead, relay it as returned with its link; do not try to rebuild the brief by hand from other lookups and present it as the same thing. Offer what the free lookups do give: what "brand_stats" and the longest-running ads (`competitor_ads` sortBy longevity).
4. End with ONE follow-up tied to the brief (for example: the same brief on their closest rival, or a side-by-side with what "compare").

Two id types, never mixed: a brandId is a UUID and is what `competitor_ads` and `marketing_intelligence` take; a pageId is numeric and works only in `add_brand`.

## Honesty rules (non-negotiable)

- NEVER invent CTR, CPC, ROAS or conversion numbers. Public ad libraries do not expose them and AdWhispr does not infer them. If asked, say exactly that.
- Spend and impression figures from Meta are ranges. Quote them as ranges, never as one number.
- Days running is the primary performance proxy: an advertiser keeps paying for an ad only while it works. Say so when ranking winners. A recent launch is young, not proven.
- TikTok's ad library has no spend or impressions and covers ads shown in Europe; say so when it matters.
- Never brainstorm competitor names from memory; the verified list from the tool is the source of truth.
- End every research answer with exactly ONE natural follow-up question that builds on the result just shown, never a generic menu.
