---
name: startup-metrics
description: Startup metrics and frameworks for founders. Use when user wants to assess product-market fit, calculate unit economics, analyze churn, project runway, diagnose funnel conversion, identify growth curves, assess competitive moats, or check fundraise readiness. Triggers on "PMF", "product-market fit", "CAC", "LTV", "churn", "runway", "burn rate", "unit economics", "funnel", "hockey stick", "J-curve", "moat", or /startup commands.
---

# Startup Metrics Skill

Turn startup jargon into actionable analysis using YOUR actual numbers. Not textbook definitions — real calculations, benchmarks, and verdicts.

## Commands

| Command | What it does |
|---------|-------------|
| `/startup:pmf` | Product-Market Fit assessment (Sean Ellis test + retention curves) |
| `/startup:unit` | Unit economics calculator (CAC, LTV, payback, margins) |
| `/startup:churn` | Churn diagnosis (logo vs revenue, cohorts, recovery) |
| `/startup:runway` | Burn rate + runway projection with scenarios |
| `/startup:funnel` | Funnel math + bottleneck identification |
| `/startup:growth` | Growth curve analysis (J-curve, hockey stick, linear, flat) |
| `/startup:moat` | Competitive moat assessment (7 moat types) |
| `/startup:ready` | Fundraise readiness scorecard |
| `/startup:glossary` | Explain any startup term using your actual numbers |
| `/startup:help` | Command reference |

---

## Stage 1: Product-Market Fit (`/startup:pmf`)

**Goal:** Assess whether you've found PMF — with data, not gut feel.

### The Sean Ellis Test

The gold standard: survey users with "How would you feel if you could no longer use [product]?"

```
SEAN ELLIS PMF TEST
=====================
Responses collected:     ___

"Very disappointed":     ___%
"Somewhat disappointed": ___%
"Not disappointed":      ___%

PMF THRESHOLD: 40%+ "Very disappointed" = PMF achieved
```

### Interpreting Results

| Score | Verdict | Action |
|-------|---------|--------|
| 40%+ | PMF achieved | Scale acquisition. Focus on growth loops. |
| 25-39% | Almost there | Segment — you likely have PMF for a subset. Find them. |
| 10-24% | Not yet | Product needs work. Go back to `/dt:empathize`. |
| <10% | Wrong market | Pivot the ICP or the product. Don't scale. |

### Segment Analysis

When overall score is 25-39%, segment by:

```
SEGMENT ANALYSIS
=================
Segment              | "Very disappointed" | Sample size | PMF?
─────────────────────┼─────────────────────┼─────────────┼─────
All users            |        ___%         |     ___     |
Completed onboarding |        ___%         |     ___     |
Weekly active users  |        ___%         |     ___     |
Power users (daily)  |        ___%         |     ___     |
Paid users           |        ___%         |     ___     |
Industry: ________   |        ___%         |     ___     |
Role: ________       |        ___%         |     ___     |
```

**Key insight:** You often have PMF for a segment before you have it overall. Find the segment, double down, expand later.

### Retention Curves (Alternative PMF Signal)

If you don't have survey data, retention curves tell the story:

```
RETENTION CURVE ANALYSIS
==========================
Cohort:    [Month/week]
Metric:    [DAU, WAU, or key action]

Week 1:    100%
Week 2:    ___%
Week 4:    ___%
Week 8:    ___%
Week 12:   ___%

CURVE SHAPE:
  Flattening (levels off at X%): PMF signal ✓
  Declining to zero:             No PMF ✗
  Smiling (dips then rises):     Re-engagement working, investigate why
```

A retention curve that flattens — even at 10% — means SOMEONE finds lasting value. Find out who and why.

### Leading Indicators (Pre-PMF)

Before you have enough data for Sean Ellis or retention:

```
PRE-PMF SIGNALS
================
[ ] Organic word-of-mouth (users you didn't acquire) — STRONGEST signal
[ ] Users coming back without prompts/emails
[ ] Users hacking workarounds for missing features (they care enough to try)
[ ] Support requests asking for MORE, not complaining about bugs
[ ] Usage increasing week-over-week without marketing spend
[ ] Users voluntarily paying (even a small amount)

Signals present: ___/6
If 4+: likely approaching PMF. Quantify with Sean Ellis test.
If 0-2: keep iterating on the core value proposition.
```

### Output
Deliver: Sean Ellis score + segment analysis + retention curve shape + verdict + specific next action.

---

## Stage 2: Unit Economics (`/startup:unit`)

**Goal:** Know your numbers. CAC, LTV, margins, and whether your business model actually works.

### Core Metrics

Ask the user for their numbers, then calculate:

```
UNIT ECONOMICS
===============

ACQUISITION
  Marketing spend (monthly):           $___
  Sales spend (monthly):               $___
  New customers acquired (monthly):    ___
  ─────────────────────────────────────────
  CAC (Customer Acquisition Cost):     $___
    = (marketing + sales spend) / new customers

LIFETIME VALUE
  ARPU (Avg Revenue Per User/month):   $___
  Gross margin:                        ___%
  Average customer lifespan (months):  ___
  ─────────────────────────────────────────
  LTV (Lifetime Value):                $___
    = ARPU × gross margin × lifespan

RATIOS
  LTV:CAC ratio:                       ___x
  Payback period:                      ___ months
    = CAC / (ARPU × gross margin)
  Contribution margin per customer:    $___
    = LTV - CAC
```

### Benchmarks

```
LTV:CAC BENCHMARKS
====================
Ratio      | Verdict
───────────┼─────────────────────────────────────────────
< 1x       | Losing money on every customer. Stop spending.
1-2x       | Barely breaking even. Fix retention or reduce CAC.
3x         | Healthy. The benchmark VCs look for.
3-5x       | Strong. Consider spending more on acquisition.
> 5x       | Possibly under-investing in growth. Scale up.

PAYBACK PERIOD BENCHMARKS
===========================
Period     | Verdict
───────────┼─────────────────────────────────────────────
< 6 months | Excellent. Cash-efficient growth possible.
6-12 months| Healthy. Standard for SaaS.
12-18 months| Concerning. Need funding to grow.
> 18 months| Dangerous. Fix pricing or churn first.
```

### When Numbers Are Missing

If the user doesn't know exact numbers, help them estimate:

```
ESTIMATION SHORTCUTS
=====================
Don't know CAC?
  → Total marketing spend last 3 months / total new customers last 3 months

Don't know lifespan?
  → 1 / monthly churn rate (e.g., 5% churn = 20 month lifespan)

Don't know gross margin?
  → SaaS: typically 70-85%
  → Marketplace: typically 15-30% (of GMV)
  → Services: typically 40-60%
  → E-commerce: typically 30-50%

Don't know ARPU?
  → MRR / total paying customers
```

### Output
Deliver: Complete unit economics table + LTV:CAC ratio + payback period + benchmark comparison + verdict + recommendations.

---

## Stage 3: Churn Diagnosis (`/startup:churn`)

**Goal:** Understand why customers leave and what to do about it.

### Churn Types

```
CHURN BREAKDOWN
================
LOGO CHURN (customer count)
  Customers at start of month:   ___
  Customers lost during month:   ___
  Logo churn rate:               ___%
    = customers lost / customers at start

REVENUE CHURN (MRR)
  MRR at start of month:        $___
  MRR lost from churned:        $___
  MRR gained from expansion:    $___
  Gross revenue churn:           ___%
    = MRR lost / MRR at start
  Net revenue churn:             ___%
    = (MRR lost - MRR expansion) / MRR at start

NET NEGATIVE CHURN: ___  (yes/no)
  If expansion revenue > lost revenue, you have net negative churn.
  This is the holy grail — existing customers grow faster than they leave.
```

### Churn Benchmarks

```
MONTHLY CHURN BENCHMARKS (SaaS)
==================================
Segment        | Good    | Acceptable | Concerning
───────────────┼─────────┼────────────┼──────────
SMB            | < 3%    | 3-5%       | > 5%
Mid-market     | < 1.5%  | 1.5-2.5%  | > 2.5%
Enterprise     | < 0.5%  | 0.5-1%    | > 1%
Consumer/B2C   | < 5%    | 5-8%      | > 8%

ANNUAL EQUIVALENTS (for context):
  2% monthly = 21.5% annual
  5% monthly = 46.0% annual
  8% monthly = 63.2% annual
```

### Churn Reason Taxonomy

Categorize every churn into one of these buckets:

```
CHURN REASONS
==============
PRODUCT (you can fix)
  [ ] Missing feature they expected
  [ ] Bug or reliability issue
  [ ] Onboarding failure (never reached aha moment)
  [ ] Performance too slow

FIT (you might fix)
  [ ] Outgrew your product (moved to enterprise tool)
  [ ] Wrong ICP (should never have been a customer)
  [ ] Seasonal use case (only needed it temporarily)

EXTERNAL (you can't fix)
  [ ] Company went out of business
  [ ] Budget cuts / downsizing
  [ ] Champion left the company
  [ ] Acquired / merged

PRICE (you can test)
  [ ] Too expensive for perceived value
  [ ] Found a cheaper alternative
  [ ] Downgraded but stayed (not full churn)

INVOLUNTARY (you must fix)
  [ ] Failed payment / card expired
  [ ] Dunning emails not set up
  [ ] Account deactivated by error
```

### Cohort Analysis Framework

```
COHORT RETENTION TABLE
========================
         Month 0  Month 1  Month 2  Month 3  Month 4  Month 5  Month 6
Jan '26:  100%     ___%     ___%     ___%     ___%     ___%     ___%
Feb '26:  100%     ___%     ___%     ___%     ___%     ___%
Mar '26:  100%     ___%     ___%     ___%     ___%
Apr '26:  100%     ___%     ___%     ___%
May '26:  100%     ___%     ___%

LOOK FOR:
  - Are newer cohorts retaining better? (product improving)
  - Is there a cliff at Month X? (onboarding or aha moment issue)
  - Do cohorts flatten? (you have a retained core)
```

### Recovery Playbook

```
CHURN RECOVERY ACTIONS
========================
Prevention (before they churn):
  [ ] Usage-drop alert (activity < 50% of average for 2+ weeks)
  [ ] Proactive outreach at risk signals
  [ ] Health score per account (usage × recency × breadth)
  [ ] QBRs for high-value accounts

Intervention (during cancellation):
  [ ] Cancel flow with reason selection (feeds taxonomy above)
  [ ] Offer pause instead of cancel
  [ ] Offer downgrade instead of cancel
  [ ] Human outreach for high-LTV accounts

Win-back (after they churn):
  [ ] 30-day win-back email (what's changed since they left)
  [ ] 90-day win-back (major feature announcement)
  [ ] Involuntary churn: auto-retry failed payments + dunning sequence
```

### Output
Deliver: Churn rates (logo + revenue) + benchmark comparison + reason taxonomy analysis + cohort table + recovery recommendations.

---

## Stage 4: Runway (`/startup:runway`)

**Goal:** How many months until the money runs out? And what can you do about it?

### Runway Calculator

```
RUNWAY PROJECTION
==================
Cash in bank:                    $___
Monthly revenue (MRR):           $___
Monthly expenses:                $___
Monthly burn rate:               $___
  = expenses - revenue (gross burn = expenses, net burn = expenses - revenue)

RUNWAY:                          ___ months
  = cash / net burn rate

DEFAULT ALIVE?                   ___
  (Paul Graham's question: if you stop fundraising and
   maintain current growth rate, do you ever become profitable?)
```

### Scenario Modeling

```
SCENARIOS
==========
                    | Maintain  | Cut 20%   | Accelerate
────────────────────┼───────────┼───────────┼───────────
Monthly burn:       | $___      | $___      | $___
Monthly revenue:    | $___      | $___      | $___
Growth rate:        | ___%      | ___%      | ___%
Runway:             | ___ mo    | ___ mo    | ___ mo
Break-even in:      | ___ mo    | ___ mo    | ___ mo
Cash needed:        | $___      | $___      | $___

RECOMMENDATION: [maintain / cut / accelerate] because [reason]
```

### Burn Rate Benchmarks

```
BURN RATE CONTEXT
==================
Stage              | Typical monthly burn | Notes
───────────────────┼──────────────────────┼─────────────
Pre-seed (1-3 ppl) | $10-30K              | Mostly salaries
Seed (3-8 ppl)     | $50-150K             | Team + tools + small marketing
Series A (8-20 ppl)| $150-400K            | Growth hiring + acquisition spend
Series B+          | $400K-1M+            | Scaling everything

MINIMUM SAFE RUNWAY:
  Pre-fundraise: 18+ months (need 6mo buffer for fundraising)
  Post-fundraise: 12+ months before next raise
  "Danger zone": < 6 months with no revenue path
```

### Key Decision Framework

```
RUNWAY DECISION TREE
======================
> 18 months:  Safe. Focus on growth and PMF.
12-18 months: Start planning next fundraise or path to profitability.
6-12 months:  URGENT. Cut non-essential spend. Start fundraising NOW.
< 6 months:   EMERGENCY. Cut to bare minimum. Bridge round or profitability.

If DEFAULT ALIVE = yes:
  → You have optionality. Fundraise from a position of strength.

If DEFAULT ALIVE = no:
  → You MUST either raise, cut, or grow faster. No other options.
```

### Output
Deliver: Runway calculation + 3 scenarios + default alive assessment + specific recommendations.

---

## Stage 5: Funnel Math (`/startup:funnel`)

**Goal:** Find where customers drop off and how to fix it.

### Funnel Framework

```
CONVERSION FUNNEL
==================
Stage           | Count    | Conv. rate | Benchmark
────────────────┼──────────┼────────────┼──────────
Visitors        | ___      |            |
 → Signups      | ___      | ___%       | 2-5% (SaaS)
 → Activated    | ___      | ___%       | 20-40%
 → Engaged      | ___      | ___%       | 30-60%
 → Paying       | ___      | ___%       | 2-10% (freemium), 15-30% (trial)
 → Retained     | ___      | ___%       | see churn benchmarks

BIGGEST DROP-OFF: _________ → _________ (___% lost)
```

### Benchmarks by Model

```
CONVERSION BENCHMARKS
======================
MODEL: Freemium
  Visitor → Signup:     2-5%
  Signup → Activated:   20-40%
  Free → Paid:          2-5% (Slack-like)
                        5-10% (mid-market)

MODEL: Free Trial (no CC)
  Visitor → Signup:     5-15%
  Signup → Activated:   30-50%
  Trial → Paid:         15-25%

MODEL: Free Trial (CC required)
  Visitor → Signup:     1-3%
  Signup → Activated:   50-70%
  Trial → Paid:         40-60%

MODEL: Sales-Led
  Visitor → Lead:       1-3%
  Lead → SQL:           10-20%
  SQL → Opportunity:    30-50%
  Opportunity → Closed: 15-30%
```

### Bottleneck Diagnosis

```
BOTTLENECK IDENTIFICATION
============================
For each stage transition, compare your rate to benchmark:

Stage               | Your rate | Benchmark | Gap    | Priority
────────────────────┼───────────┼───────────┼────────┼─────────
Visitor → Signup    | ___%      | ___%      | ___%   |
Signup → Activated  | ___%      | ___%      | ___%   |
Activated → Paying  | ___%      | ___%      | ___%   |
Paying → Retained   | ___%      | ___%      | ___%   |

LARGEST GAP = your #1 bottleneck.

Fix priority: activation > retention > conversion > traffic.
(No point driving traffic to a leaky funnel.)
```

### Funnel Math

Show the compounding impact of fixing each stage:

```
IMPACT MODELING
================
Current: 10,000 visitors → ___ signups → ___ active → ___ paying = $___/mo

Scenario A: Fix signup rate (2% → 4%)
  10,000 → ___ signups → ___ active → ___ paying = $___/mo (+___%)

Scenario B: Fix activation (25% → 40%)
  10,000 → ___ signups → ___ active → ___ paying = $___/mo (+___%)

Scenario C: Fix conversion (5% → 8%)
  10,000 → ___ signups → ___ active → ___ paying = $___/mo (+___%)

HIGHEST IMPACT: Scenario ___ (+___%)
```

### Output
Deliver: Funnel table with conversion rates + benchmark comparison + bottleneck identification + impact modeling + fix recommendation.

---

## Stage 6: Growth Curve Analysis (`/startup:growth`)

**Goal:** Identify what growth phase you're in and what to expect next.

### Growth Curve Types

```
GROWTH CURVES
==============

J-CURVE (most startups)
  ╲
   ╲___________╱
                 ╱
               ╱
             ╱
  Phase 1: Dip (spending > earning, building, iterating)
  Phase 2: Inflection (PMF found, economics work)
  Phase 3: Acceleration (compounding growth)

HOCKEY STICK
  ____________╱
              ╱
  Long flat → sudden acceleration
  Usually triggered by: viral moment, PR hit, platform change,
  or hitting critical mass in a network effect

LINEAR
  ╱
  ╱
  ╱
  Steady, predictable growth. Not bad — but won't attract VC funding.
  Common in services, agencies, and bootstrapped SaaS.

S-CURVE
  ___________
             ╱
           ╱
  ________╱
  Slow start → rapid growth → plateau (market saturated)
  Healthy. Time to find the next S-curve (new market, new product).

FLAT / DECLINING
  ──────────___
                ╲
  Stagnation. Either no PMF, market saturated, or execution problem.
```

### Diagnose Your Curve

```
GROWTH DIAGNOSIS
=================
Metric:                    [MRR / users / revenue]
Time period:               [last 6-12 months]

Month 1:    ___
Month 2:    ___  (___% MoM)
Month 3:    ___  (___% MoM)
Month 4:    ___  (___% MoM)
Month 5:    ___  (___% MoM)
Month 6:    ___  (___% MoM)

Average MoM growth:        ___%
Trend (accelerating/steady/decelerating): ___

CURVE TYPE:    ___
PHASE:         ___
```

### Growth Rate Benchmarks

```
MoM GROWTH RATE BENCHMARKS
=============================
Rate       | Grade | Context
───────────┼───────┼───────────────────────────────────
> 20% MoM  | A+    | Top decile. YC-caliber growth.
15-20% MoM | A     | Excellent. Series A-ready.
10-15% MoM | B     | Good. Keep compounding.
5-10% MoM  | C     | Decent for bootstrapped. Slow for VC.
< 5% MoM   | D     | Stalling. Diagnose why.
Negative    | F     | Declining. Urgent action needed.

CONTEXT: 10% MoM = 3.1x annual. 20% MoM = 8.9x annual.

T2D3 FRAMEWORK (for VC-backed SaaS):
  Year 1-2: Triple revenue (3x)
  Year 3-5: Double revenue (2x)
  $1M ARR → $3M → $9M → $18M → $36M → $72M
```

### Output
Deliver: Growth data plotted + curve type + phase diagnosis + growth rate grade + what to expect next + recommended actions for current phase.

---

## Stage 7: Competitive Moat Assessment (`/startup:moat`)

**Goal:** Assess how defensible your business is — and what to strengthen.

### Seven Moat Types

Score each moat type (0-5) for your business:

```
MOAT ASSESSMENT
================
Moat Type              | Score (0-5) | Evidence
───────────────────────┼─────────────┼────────────────────
Network Effects        |    /5       | [More users = more value?]
Switching Costs        |    /5       | [Cost/pain of leaving?]
Economies of Scale     |    /5       | [Cheaper at volume?]
Brand / Trust          |    /5       | [Would users pay more for your name?]
Data Advantage         |    /5       | [Data that improves with use?]
Regulatory / Legal     |    /5       | [Licenses, patents, compliance?]
Counter-positioning    |    /5       | [Incumbents can't copy without hurting themselves?]
────────────────────────────────────────────────────────────
TOTAL MOAT SCORE:      ___/35

MOAT STRENGTH:
  28-35: Fortress (extremely defensible)
  21-27: Strong (multiple defensible layers)
  14-20: Moderate (some defensibility, needs strengthening)
  7-13:  Weak (vulnerable to well-funded competitors)
  0-6:   No moat (competing on execution alone)
```

### Moat Deepening Strategies

```
MOAT DEEPENING PLAYBOOK
=========================
Network Effects (score < 3):
  → Add collaboration features (multi-user = sticky)
  → Build a marketplace or community layer
  → Create integrations that connect users

Switching Costs (score < 3):
  → Store user data in proprietary formats
  → Build workflows that accumulate over time
  → Offer migration from competitors, never to competitors

Data Advantage (score < 3):
  → Use product usage data to improve the product
  → Build features that get better with more customers
  → Create benchmarks / insights only possible with aggregate data

Counter-positioning (score < 3):
  → Identify what incumbents CAN'T do without cannibalizing revenue
  → Build your product around that gap
  → Example: Notion vs Microsoft — bundled simplicity vs unbundled complexity
```

### "Can a Big Company Copy This?" Test

```
COPY RISK ASSESSMENT
======================
If [biggest competitor] copied your product tomorrow:

1. How long to build?          ___ months
2. Would their users adopt it? ___
3. Would it hurt their core?   ___
4. Do they have your data?     ___
5. Do they have your brand?    ___

If answers are: short, yes, no, yes, no → HIGH RISK, you need a moat
If answers are: long, no, yes, no, yes → LOW RISK, you have defensibility
```

### Output
Deliver: Moat scorecard (7 types) + total score + weakest moat identified + specific deepening recommendations + copy risk assessment.

---

## Stage 8: Fundraise Readiness (`/startup:ready`)

**Goal:** Score whether your startup is ready to raise — and what to fix first.

### Fundraise Readiness Scorecard

```
FUNDRAISE READINESS SCORECARD
================================

TRACTION (30 points)
  [ /10 ] Revenue growth rate (MoM or YoY)
  [ /10 ] User growth and engagement metrics
  [ /10 ] PMF evidence (Sean Ellis score, retention curves)

UNIT ECONOMICS (20 points)
  [ /10 ] LTV:CAC ratio (≥ 3x for full marks)
  [ /5  ] Payback period (< 12 months)
  [ /5  ] Gross margin (> 70% for SaaS)

MARKET (15 points)
  [ /5  ] TAM size and credibility of estimate
  [ /5  ] Growth of target market
  [ /5  ] Competitive positioning clarity

TEAM (15 points)
  [ /5  ] Founder-market fit (relevant experience)
  [ /5  ] Technical co-founder or team capability
  [ /5  ] Key hires made or identified

PRODUCT (10 points)
  [ /5  ] Product maturity (beyond MVP?)
  [ /5  ] Clear roadmap with customer-validated priorities

NARRATIVE (10 points)
  [ /5  ] Can explain the business in 1 sentence
  [ /5  ] Compelling "why now" and "why us" story

TOTAL: ___/100
```

### Score Interpretation

| Score | Verdict | Action |
|-------|---------|--------|
| 80-100 | Ready to raise | Polish the deck, start outreach |
| 60-79 | Almost ready | Fix the weakest category first |
| 40-59 | Not yet | 2-3 months of focused work needed |
| <40 | Too early | Build more, prove more, then reassess |

### What VCs Actually Look For (by Stage)

```
VC EXPECTATIONS BY STAGE
==========================
PRE-SEED ($500K-2M)
  Team + vision + early signal
  PMF not required, but must show insight
  "Why will this be massive?"

SEED ($2-5M)
  Early PMF signal + initial traction
  $5-50K MRR or strong usage metrics
  "Show me the retention curve"

SERIES A ($5-15M)
  Clear PMF + repeatable growth
  $100K+ MRR, growing 15%+ MoM
  Unit economics trending positive
  "Show me the growth machine"

SERIES B ($15-50M)
  Proven unit economics at scale
  $500K+ MRR, clear path to $10M ARR
  Sales/marketing engine working
  "Show me the path to market leadership"
```

### Common Fundraise Killers

```
RED FLAGS VCS SPOT IMMEDIATELY
=================================
[ ] High churn with no explanation
[ ] CAC increasing while growth slows
[ ] No clear ICP ("our market is everyone")
[ ] Burn rate doesn't match stage
[ ] Cap table problems (too many investors, bad terms)
[ ] No technical co-founder for a tech product
[ ] Competitor already raised 10x more and has traction
[ ] "AI wrapper" with no proprietary data or model
[ ] Revenue concentration (one customer = 50%+ of MRR)
[ ] Founders can't articulate unit economics
```

### Output
Deliver: Readiness scorecard + total score + weakest areas + stage-appropriate expectations + red flag check + specific fixes before fundraising.

---

## Stage 9: Startup Glossary (`/startup:glossary`)

**Goal:** Explain any startup term using the user's actual numbers — not textbook definitions.

### How to Use

When the user asks about a term, don't just define it. Calculate it with their data if available, show what "good" looks like, and connect it to their situation.

### Core Terms

```
METRICS
  MRR    — Monthly Recurring Revenue. Sum of all active subscriptions this month.
  ARR    — Annual Recurring Revenue. MRR × 12. The number VCs use for SaaS valuations.
  ARPU   — Average Revenue Per User. MRR / total paying customers.
  ACV    — Annual Contract Value. Average annual deal size.
  NRR    — Net Revenue Retention. Revenue from existing customers this year / last year.
           > 100% = expansion. > 120% = exceptional.
  GMV    — Gross Merchandise Value. Total transaction volume (for marketplaces).

ACQUISITION
  CAC    — Customer Acquisition Cost. Total sales + marketing spend / new customers.
  Blended CAC — All-channel CAC (including organic). Usually lower than paid CAC.
  Paid CAC    — Only paid channel spend / customers from paid channels.
  CPA    — Cost Per Acquisition. Same as CAC in most contexts.
  CPL    — Cost Per Lead. Marketing spend / leads generated.

RETENTION
  LTV    — Lifetime Value. ARPU × gross margin × lifespan.
  Churn  — % of customers (logo) or revenue lost per period.
  Cohort — Group of customers who started at the same time. Used to compare retention.
  DAU/MAU — Daily/Monthly Active Users. DAU/MAU ratio measures engagement (> 20% = good).

GROWTH
  MoM    — Month-over-Month growth rate.
  CMGR   — Compound Monthly Growth Rate. Smoothed average over a period.
  K-factor — Viral coefficient. Invites × conversion rate. > 1 = viral growth.
  T2D3   — Triple-triple-double-double-double. VC growth benchmark.

FUNDRAISING
  TAM    — Total Addressable Market. Revenue if you had 100% market share.
  SAM    — Serviceable Addressable Market. TAM you can actually reach.
  SOM    — Serviceable Obtainable Market. SAM you'll realistically capture.
  Burn rate — Monthly cash spent (gross = total, net = expenses minus revenue).
  Runway — Cash / net burn rate = months until out of money.
  Dilution — % of ownership given up per funding round.

PRODUCT
  PMF    — Product-Market Fit. Validated demand for your product in your market.
  PQL    — Product-Qualified Lead. User whose product usage signals sales readiness.
  PQA    — Product-Qualified Account. Same concept at company level (better for B2B).
  TTV    — Time to Value. How quickly a new user reaches the aha moment.
  Aha moment — The action that makes a user "get it" and become likely to stay.
```

### Output
Deliver: Definition + calculation using their numbers (if available) + benchmark + what it means for their specific situation.

---

## Integration Notes

- **Feeds from DT:** `/dt:empathize` identifies user pain → `/startup:pmf` validates they want a solution
- **Feeds from GTM:** `/gtm:positioning` defines ICP → `/startup:unit` proves you can profitably serve them
- **Feeds to GTM:** `/startup:funnel` finds bottlenecks → `/gtm:landing` fixes the conversion page
- **Feeds to GTM:** `/startup:churn` identifies reasons → `/gtm:growth` builds retention loops
- **Feeds to Pitch:** `/startup:ready` identifies gaps → fix them → then raise

## Principles

1. **Numbers over narratives.** "We're growing fast" means nothing. "18% MoM over 6 months" means everything.
2. **Segment before you despair.** Overall metrics hide pockets of PMF, healthy cohorts, and power users.
3. **Fix the leakiest bucket first.** Activation > retention > conversion > traffic. Always.
4. **Default alive is the question.** If you can't answer it, calculate it now with `/startup:runway`.
5. **Benchmarks are context, not targets.** A 2% churn rate is terrible for enterprise SaaS and amazing for consumer.
6. **Your moat is what you're building, not what you have.** Score it honestly. Strengthen the weakest point.
7. **Fundraise readiness is not fundraise timing.** Being ready doesn't mean you should raise. Being ready means you CAN when you choose to.
