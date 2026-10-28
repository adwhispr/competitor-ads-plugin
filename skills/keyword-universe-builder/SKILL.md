---
name: keyword-universe-builder
description: "Build a complete keyword universe for any product or topic with real Google Keyword Planner data in about 180 countries and 35 languages. Use when the user wants keyword research, search volumes, cost-per-click estimates, or a keyword list for a new campaign or market."
---

# Keyword universe builder

## First run: the user probably is NOT connected yet

If the adwhispr-competitor-ads server shows as needing authentication, or a tool call fails with an authentication error, do NOT apologize and stop. Treat connecting as step one:

1. Connecting is free, takes one click, and there are no API keys to manage. No ad account is needed; this is research only.
2. Claude Code: run /mcp, choose "adwhispr-competitor-ads", pick Authenticate. Claude.ai or Cowork: open Settings -> Plugins -> AdWhispr Competitor Ads and use its sign-in prompt, or the authentication card Claude shows when a tool first needs it.
3. Tell them the payoff: "the second you're connected, name a product and a country and I'll build the keyword list with real search volumes."
4. A free account is enough to start. After they connect, continue right where the request left off.

Real Keyword Planner data, average monthly searches and cost-per-click ranges, for any topic, in nearly any country and language.

## How it runs

1. Confirm the topic or product and the market (country plus language). Non-US and non-English markets work.
2. `marketing_intelligence` what "keywords" with seedKeywords, country, language (limit up to the default 30 per call). Run 2 or 3 seed variations to widen the universe: product terms, problem terms, brand-adjacent terms.
3. Group results by intent: buy-now, comparison, problem or informational. Flag the high-intent, affordable middle.
4. Optionally cross-reference a competitor with what "site_keywords" (competitorUrl) to find terms the user is missing, framed as a content proxy.
5. End with ONE follow-up. Building the Search campaign itself is the AdWhispr Ads Manager plugin's job; this plugin is research only.

## Honesty rules

- Volumes and costs per click are Google's estimates and ranges; quote them that way.
- A thin result in a small market is reported as thin, not padded with invented terms.
