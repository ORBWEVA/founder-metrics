---
name: niche-validator
description: Validate and score a niche idea (or compare 2-3) across keyword volume, competition, willingness-to-pay, buildability, and flippability. Returns a 1-10 weighted score with go/conditional/no-go verdict. Triggers on "validate niche", "score idea", "should I build", "is this niche worth it", or /niche-validator.
---

# Niche Validator

Score a niche idea (or compare 2-3) and return a go/conditional/no-go verdict.

## Slash command

`/niche-validator` — single entry point. Detects whether the user supplied 1 niche (validate flow) or 2-3 niches (compare flow).

## Validate flow (1 niche)

**Input**: Niche idea (e.g., "AI resume builder for nurses")

### Process
1. **Keyword research** — search volume for primary + related keywords (DataForSEO, Google Trends, web search)
2. **Competitor scan** — count direct competitors, note funding levels, identify market leaders
3. **TAM estimation** — addressable market size from industry reports or bottoms-up calc
4. **Scoring** — rate each dimension 1-10

### Scoring Dimensions

| Dimension | Weight | 1 (Bad) | 5 (Okay) | 10 (Great) |
|-----------|--------|---------|----------|------------|
| **Volume** | 20% | <100 searches/mo | 1K-5K | >10K |
| **Competition** | 20% | Funded incumbents, saturated | Mid-tier players | Few/no direct competitors |
| **Willingness to Pay** | 25% | Free alternatives dominate | Some paid tools exist | Buyers actively spending |
| **Buildability** | 15% | 6+ months, team needed | 2-3 months solo | MVP in 2-4 weeks |
| **Flippability** | 20% | No acquisition interest | Niche acquirers exist | Active M&A in space |

> Competition is **inverted**: fewer competitors = higher score.

### Weighted Score Formula
```
Score = (Volume × 0.20) + (Competition × 0.20) + (WTP × 0.25) + (Buildability × 0.15) + (Flippability × 0.20)
```

### Go/No-Go Thresholds
- **8-10**: Strong go. Build immediately.
- **6-7.9**: Conditional go. Validate WTP before building.
- **4-5.9**: Weak. Needs a unique angle or pivot.
- **1-3.9**: No-go. Move on.

### Output Template

```markdown
## Niche Validation: [Niche Name]

**Primary keywords**: [keyword1] ([vol]/mo), [keyword2] ([vol]/mo)
**Direct competitors**: [count] ([list top 3])
**TAM**: $[amount] ([source])

| Dimension | Score | Rationale |
|-----------|-------|-----------|
| Volume | X/10 | ... |
| Competition | X/10 | ... |
| Willingness to Pay | X/10 | ... |
| Buildability | X/10 | ... |
| Flippability | X/10 | ... |

**Weighted Score: X.X/10**
**Verdict: [GO / CONDITIONAL / NO-GO]**

### Key Risks
- ...

### Recommended Next Steps
1. ...
```

## Compare flow (2-3 niches)

**Input**: 2-3 niche ideas

### Process
1. Run the validate flow on each niche (parallel where possible)
2. Output side-by-side comparison table
3. Recommend the strongest option with reasoning

### Output Template

```markdown
## Niche Comparison

| Dimension | [Niche A] | [Niche B] | [Niche C] |
|-----------|-----------|-----------|-----------|
| Volume | X/10 | X/10 | X/10 |
| Competition | X/10 | X/10 | X/10 |
| Willingness to Pay | X/10 | X/10 | X/10 |
| Buildability | X/10 | X/10 | X/10 |
| Flippability | X/10 | X/10 | X/10 |
| **Weighted Score** | **X.X** | **X.X** | **X.X** |

**Recommendation**: [Niche X] because...
```

## Data Sources
- **Volume**: Google Trends, DataForSEO keyword data, web search
- **Competition**: Web search for "[niche] SaaS", ProductHunt, G2, Capterra
- **TAM**: Industry reports, bottoms-up (audience size × avg price × frequency)
- **WTP**: Existing pricing pages, Reddit/forum complaints about paying for solutions
- **Flippability**: Acquire.com listings, recent acquisitions in space, PE/VC activity
