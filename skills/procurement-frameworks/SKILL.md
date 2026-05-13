---
name: procurement-frameworks
version: "1.0.0"
description: Methodology library for procurement decision-making — 5R, Kraljic Matrix, Carter 10Cs, TCO, ABC/XYZ, and negotiation leverage selection
---

# Procurement Frameworks

Reusable, category-agnostic frameworks for sourcing analysis and supplier decision-making.

## Use When

- Building a comparison or recommendation that needs an explicit decision rationale
- Positioning a category in the supplier-buyer power map
- Calculating true cost beyond unit price
- Structuring a negotiation prep doc
- Prioritizing items inside a long requirement list

## The 5R Model

Five dimensions every sourcing recommendation must satisfy:

| R | Question to answer |
|---|---|
| **Right item** | Does the spec actually meet the use case? Over-spec = waste; under-spec = rework |
| **Right quantity** | MOQ, EOQ, safety stock, packaging unit alignment |
| **Right price** | Total landed cost vs market reference (median + range) |
| **Right time** | Lead time vs need-by date; expedite cost; seasonal price windows |
| **Right source** | Supplier capacity, qualification, geographic / political risk, single-source dependency |

Score each R on a 0-5 scale; flag any score <= 2 as a blocker.

## Kraljic Matrix

Position the item by **profit impact (high/low)** vs **supply risk (high/low)**:

| Quadrant | Sourcing strategy |
|---|---|
| **Strategic** (high impact, high risk) | Long-term partnership, dual-source insurance, joint development |
| **Leverage** (high impact, low risk) | Aggressive bidding, volume consolidation, e-auction |
| **Bottleneck** (low impact, high risk) | Inventory buffer, alternative qualification, contingency plan |
| **Non-critical** (low impact, low risk) | Catalog purchase, automate, pool with other categories |

Always cite the quadrant and the matching strategy in the recommendation.

## Carter's 10Cs (Supplier Pre-Qualification)

| C | Check |
|---|---|
| **Competence** | Can they technically do it? Past projects, team, certifications |
| **Capacity** | Production / service throughput vs your demand |
| **Commitment** | Quality program, ISO/SLA evidence, key-account treatment |
| **Control** | Process control, change management, traceability |
| **Cash** | Financial stability — liquidity, leverage, payment cycle |
| **Cost** | True total cost competitiveness, not just unit price |
| **Consistency** | Track record across deliveries, defect rate, response time |
| **Culture** | Communication style, risk transparency, ethics fit |
| **Clean** | Compliance, ESG, environmental, sanctions, labor |
| **Communication** | Reachability, language, time-zone, escalation path |

Use as a pass / borderline / fail filter before deep due diligence.

## TCO Breakdown

```
TCO = Acquisition + Operation + Maintenance + Disposal + Opportunity
       (price + tax + freight + customs + install) (energy + consumables + labor) (preventive + repair + parts + downtime) (decommission + resale - residual) (lock-in cost + switching cost)
```

When TCO matters: equipment, software, vehicles, machinery, anything with multi-year service life.

Show TCO as a stacked bar across candidates; never compare on unit price alone for capex items.

## Negotiation Leverage Library

| Leverage | When to use | Sample script |
|---|---|---|
| **Volume aggregation** | When buyer can pool with other categories or sister entities | "我们今年会有 X 个项目要落，能不能给一个框架价" |
| **Payment terms** | Supplier needs cash flow | "首单全款 vs 30/60/90 账期，价格让多少" |
| **Multi-source threat** | Supplier knows you have alternatives | "我们手上 A、B、C 三家都报了，需要你今天回到 X 价位" |
| **Exclusivity / first-look** | Supplier wants a flagship case | "如果给到 X 价，我们承诺这个领域 12 个月独家" |
| **Market timing** | Off-season / fiscal-year-end / inventory clearance | "你们 Q4 任务还差 X，我现在下单是不是能多一档" |
| **Spec relaxation** | Buyer can accept B-spec or last-gen | "如果用 X 替代 Y，能省多少" |
| **Logistics handover** | Buyer can self-pick or self-ship | "我们自己拉货 / 自己报关，价格扣多少" |
| **Long-term commitment** | Stable demand worth securing | "签 18 个月固定价 + 季度复议，能给到什么价" |

Pick at most 3 leverages per negotiation — too many dilutes credibility.

## ABC / XYZ Analysis

When the brief contains a long item list (>= 20 SKUs):

- **ABC** by spend: A = top 80% spend (~20% of items), B = next 15%, C = remaining 5%
- **XYZ** by demand variability: X = stable, Y = seasonal, Z = sporadic
- **Sourcing strategy by cell**: AX = strategic partner; AZ = volatile big-ticket — buffer + flexible source; CZ = catalog automate

Use this before deep-diving any single item to focus effort on the A/B rows.

## Output Convention

When applying any framework in a report:

1. State which framework
2. Show the inputs / scores / quadrant placement
3. Derive the recommended action explicitly from the framework
4. Note any framework limitation that the audience should know

Never use a framework as decoration — every cited framework must drive a decision.
