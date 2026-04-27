---
description: Score one niche idea or compare 2-3, with go/conditional/no-go verdict
---

Use the **niche-validator** skill (`~/.claude/skills/niche-validator/SKILL.md`) to score the user's niche idea(s).

**Detect the flow:**
- 1 niche supplied → run the **validate flow** (full scoring + verdict + risks + next steps)
- 2-3 niches supplied → run the **compare flow** (side-by-side table + recommendation)

**For each niche, gather real data — do not estimate from training:**
1. Keyword search volume (DataForSEO MCP, Google Trends, or web search) — primary + 2-3 related keywords
2. Direct competitor count and top 3 names (web search "[niche] SaaS", ProductHunt, G2, Capterra)
3. TAM estimate (industry reports OR bottoms-up: audience size × avg price × frequency)
4. Pricing signals from existing tools (their landing pages)
5. Recent acquisition activity in the space (Acquire.com, news search)

**Score each dimension 1-10** per the rubric in SKILL.md, apply weights, output the templated markdown verdict.

If the user hasn't provided a niche, ask: "What niche idea(s) should I score? (one for full validation, 2-3 for comparison)"
