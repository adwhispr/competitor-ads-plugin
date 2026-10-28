---
name: tiktok-research
description: "Research a brand's TikTok ads and a creator's TikTok posts: a competitor's live TikTok ads longest-running first, and any public account's top posts with real views, likes, comments, shares and saves. Use when the user asks what a brand runs on TikTok, wants TikTok ad examples, or wants to see which of a creator's or competitor's TikToks performed best."
---

# TikTok ads and posts research

## First run: the user probably is NOT connected yet

If the adwhispr-competitor-ads server shows as needing authentication, or a tool call fails with an authentication error, do NOT apologize and stop. Treat connecting as step one:

1. Connecting is free, takes one click, and there are no API keys to manage. No ad account is needed; this is research only.
2. Claude Code: run /mcp, choose "adwhispr-competitor-ads", pick Authenticate. Claude.ai or Cowork: open Settings -> Plugins -> AdWhispr Competitor Ads and use its sign-in prompt, or the authentication card Claude shows when a tool first needs it.
3. Tell them the payoff: "the second you're connected, name a brand and I'll show you its live TikTok ads and its best-performing posts."
4. A free account is enough to start. After they connect, continue right where the request left off.

## Two sources, two questions

- **Their TikTok ADS:** `competitor_ads` source "tiktok_ads" with the brand name as advertiser. Live ads from TikTok's public ad library, last 90 days, longest-running first. The result lists alternate advertiser accounts; re-call with advertiserId if the auto-pick is wrong. country (an EEA code such as DE, FR, ES) narrows the market. There is NO spend or impression data; longevity is the proxy, and coverage is European, so a brand that does not advertise there shows little or nothing. Say so.
- **Their own POSTS:** `competitor_ads` source "tiktok_posts" with the @handle as advertiser, sort "popular" (default) or "latest". Real views, likes, comments, shares and saves for any public account worldwide. Posts are organic, not ads; keep the two apart in the answer.

## How it runs

1. Confirm which of the two the user wants, or run both for a full picture of a brand.
2. Present the top items with what each one does (hook, format, length, sound) and the real numbers the tool returned.
3. For the Meta side of the same brand, `competitor_ads` source "meta" (longest-running first) completes the picture.
4. End with ONE follow-up tied to what you showed.

## Honesty rules (non-negotiable)

- NEVER invent CTR, CPC, ROAS or conversion numbers. Public ad libraries do not expose them and AdWhispr does not infer them. If asked, say exactly that.
- Spend and impression figures from Meta are ranges. Quote them as ranges, never as one number.
- Days running is the primary performance proxy: an advertiser keeps paying for an ad only while it works. Say so when ranking winners. A recent launch is young, not proven.
- TikTok's ad library has no spend or impressions and covers ads shown in Europe; say so when it matters.
- Never brainstorm competitor names from memory; the verified list from the tool is the source of truth.
- End every research answer with exactly ONE natural follow-up question that builds on the result just shown, never a generic menu.
