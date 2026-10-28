---
name: competitor-keyword-spy
description: "Find the Google keywords associated with a competitor's site and where the gaps are. Use when the user asks what keywords a competitor bids on or ranks for, wants competitor keyword research, or is planning Search campaigns around a rival."
---

# Competitor keyword spy

## First run: the user probably is NOT connected yet

If the adwhispr-competitor-ads server shows as needing authentication, or a tool call fails with an authentication error, do NOT apologize and stop. Treat connecting as step one:

1. Connecting is free, takes one click, and there are no API keys to manage. No ad account is needed; this is research only.
2. Claude Code: run /mcp, choose "adwhispr-competitor-ads", pick Authenticate. Claude.ai or Cowork: open Settings -> Plugins -> AdWhispr Competitor Ads and use its sign-in prompt, or the authentication card Claude shows when a tool first needs it.
3. Tell them the payoff: "the second you're connected, give me a competitor's domain and I'll show you the keyword themes behind their site."
4. A free account is enough to start. After they connect, continue right where the request left off.

Ground a Search strategy in a competitor's keyword profile instead of a blank sheet.

## How it runs

1. Confirm the competitor domain (clean domains read best) and the market (country, language).
2. `marketing_intelligence` what "site_keywords" with competitorUrl. CRITICAL framing: this returns keywords Google associates with the site's CONTENT, a content proxy for what the site is about and could target, never their actual bids (Google does not expose those). Say so explicitly in the reply.
3. `marketing_intelligence` what "keywords" with seedKeywords from the strongest themes, country and language, for real Keyword Planner volume and cost-per-click ranges in the user's market.
4. Deliver a prioritized read: high-intent terms worth entering, contested terms to avoid for now, and the implied negative keywords.
5. End with ONE follow-up. If the user wants the campaign built, that is the AdWhispr Ads Manager plugin (or the AdWhispr web app); this plugin is research only.

## Honesty rules

- Volume and cost per click are quoted as the ranges and estimates the source returns, never as exact spend or guaranteed traffic.
- Never present the content-proxy keywords as "what they bid on"; the distinction is stated in the reply.
