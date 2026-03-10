# founder-metrics

Startup metrics and frameworks for Claude Code. Turn jargon into analysis using YOUR actual numbers.

## What's inside

10 slash commands that calculate, benchmark, and diagnose:

| Command | What it does |
|---------|-------------|
| `/startup:pmf` | Product-Market Fit assessment (Sean Ellis test + retention curves) |
| `/startup:unit` | Unit economics (CAC, LTV, LTV:CAC ratio, payback period) |
| `/startup:churn` | Churn diagnosis (logo vs revenue, cohorts, recovery playbook) |
| `/startup:runway` | Burn rate + runway with 3 scenarios + "default alive?" |
| `/startup:funnel` | Funnel math + bottleneck identification + impact modeling |
| `/startup:growth` | Growth curve analysis (J-curve, hockey stick, linear, flat) |
| `/startup:moat` | Competitive moat assessment (7 moat types, 0-35 score) |
| `/startup:ready` | Fundraise readiness scorecard (0-100) |
| `/startup:glossary` | Explain any startup term using your real numbers |
| `/startup:help` | Command reference |

## Install

```bash
npx skills add ORBWEVA/founder-metrics
```

Or manually copy:
- `skills/` -> `~/.claude/skills/`
- `commands/` -> `~/.claude/commands/`

## Example output

### `/startup:unit` on a SaaS product

```
UNIT ECONOMICS
===============
CAC:              $110.53
LTV:              $343.00
LTV:CAC:          3.1x (healthy — above 3x threshold)
Payback period:   2.3 months (strong — under 12mo)
Contribution:     $232.47 per customer

VERDICT: Unit economics work. You can afford to spend more on
acquisition. Consider increasing CAC budget by 30% and monitoring
whether LTV:CAC stays above 3x.
```

### `/startup:pmf` with survey data

```
SEAN ELLIS PMF TEST
=====================
Responses: 84

"Very disappointed":     31%  ← Below 40% threshold
"Somewhat disappointed": 28%
"Not disappointed":      41%

VERDICT: NOT YET at product-market fit.

SEGMENT ANALYSIS:
  Activated users:    47% "very disappointed" ← PMF HERE
  Non-activated:      12% "very disappointed"

INSIGHT: You have PMF for activated users. Your problem isn't
the product — it's activation. Fix onboarding before scaling.
```

### `/startup:runway` for an early-stage startup

```
RUNWAY PROJECTION
==================
Cash in bank:       $380,000
Monthly revenue:    $12,400
Monthly expenses:   $47,000
Net burn rate:      $34,600

RUNWAY:             11.0 months

DEFAULT ALIVE?      No (at 12% MoM growth, break-even in 18 months)

SCENARIOS:
  Maintain:    11.0 months runway
  Cut 20%:     15.8 months runway
  Accelerate:  8.2 months runway

VERDICT: URGENT. Start fundraising or cut costs now.
You need 18+ months runway to fundraise comfortably.
```

### `/startup:moat` for a B2B SaaS

```
MOAT ASSESSMENT
================
Network Effects:      1/5  (single-player tool)
Switching Costs:      3/5  (data + workflow lock-in)
Economies of Scale:   2/5  (some infra advantages)
Brand / Trust:        1/5  (early stage, no brand yet)
Data Advantage:       4/5  (usage data improves recommendations)
Regulatory:           0/5  (no regulatory barriers)
Counter-positioning:  3/5  (incumbents too complex to simplify)

TOTAL: 14/35 (Moderate — some defensibility, needs strengthening)

WEAKEST: Network Effects. Consider adding team/collaboration features.
STRONGEST: Data Advantage. Double down — make the product visibly
smarter with more usage.
```

## How the commands connect

```
VALIDATE:   /startup:pmf → /startup:unit → /startup:funnel
SUSTAIN:    /startup:churn → /startup:growth → /startup:moat
FUNDRAISE:  /startup:ready → (fix gaps) → /startup:ready again
```

## Pairs with other ORBWEVA skills

```
/dt:empathize        → understand the user
/startup:pmf         → validate the fit
/gtm:positioning     → articulate who it's for
/startup:unit        → prove the economics
/gtm:pricing         → set the right price
/gtm:landing         → convert visitors
/startup:funnel      → find where they drop off
/startup:churn       → find why they leave
/startup:growth      → identify your growth curve
/startup:runway      → how long you have
/startup:ready       → are your numbers fundable?
/startup:moat        → can someone copy this?
```

Install the full founder stack:
```bash
npx skills add ORBWEVA/dt-skill           # Design thinking
npx skills add ORBWEVA/gtm-skills         # Go-to-market + GEO + SEO
npx skills add ORBWEVA/founder-metrics    # Startup metrics
```

## Security

Zero executable code. Pure markdown — structured prompts that guide Claude's thinking. No scripts, no dependencies, no API calls, no shell commands.

```
skills/startup-metrics/SKILL.md    # All 9 stages
commands/startup/*.md              # 10 slash commands
package.json                       # metadata only
```

## License

MIT
