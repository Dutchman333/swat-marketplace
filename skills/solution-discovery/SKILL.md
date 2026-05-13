---
name: solution-discovery
version: "1.0.0"
description: Open-vision research methodology — leverage AI search and multi-source web search to surface real-world solutions, mature implementations, and KOL reviews
---

# Solution Discovery

A research methodology that forces broad, multi-source product and solution exploration so that recommendations are not restricted to mainstream brands or first-page search results.

## Use When

- The brief asks "what should I buy?" or "which solution is best?"
- A category recommendation is being prepared
- Validating that a recommended product is genuinely vetted vs hype-driven

## The 5-Source Coverage Rule

Every product or solution recommendation must cite evidence from **at least 5 distinct source types**. If fewer than 5 source types are reached, the recommendation is incomplete and must be marked "preliminary".

| # | Source type | Examples | What it tells you |
|---|---|---|---|
| 1 | **Brand official site** | manufacturer.com, official Tmall flagship, brand WeChat | Authoritative spec, warranty, MSRP |
| 2 | **Media / KOL reviews** | 小红书, 抖音, B 站, 知乎专栏, WeChat 公众号, 极客公园, 什么值得买 | Real user experience, common complaints, hidden quirks |
| 3 | **B2B platforms with transaction data** | 1688, 震坤行, JD 工业品 | Real wholesale price floor, MOQ, factory certifications |
| 4 | **Comparable project case studies** | Industry case-study sites, supplier portfolio pages, news coverage of similar deployments | Proves the spec works at scale, surfaces integration gotchas |
| 5 | **Industry reports / forums / deep-dive articles** | 艾瑞 / 易观 / 36 氪 reports, 知乎 long-form, 公众号 deep articles | Trends, market structure, blind spots not visible from product pages |

## Social Media Review Mining (sources 2)

For consumer, digital, home, beauty, parenting, travel categories — these channels often have the truest signal.

### 小红书 (Xiaohongshu)

- Search both Chinese and English terms when relevant
- Filter by **"已购买"** tag if available
- Sort by **最新** (latest) for current model insights, **最热** (hottest) for consensus
- Read the **comment sections** — complaints often live there, not in the post
- Watch for **promotional disclosure tags** (合作 / 广告) and discount filter

### 抖音 / TikTok-CN

- Use video titles + hashtags
- Watch for **"踩坑"** ("fell into a pit") and **"避雷"** ("lightning rod" = warning) videos — these surface failures
- Note creator follower count and engagement ratio for reliability weighting

### B 站 (Bilibili)

- Best for digital, audio, gaming, and analytical reviews
- Filter by view count + length (>= 5 min for substance)
- Look for **测评 / 对比 / 拆解** (review / comparison / teardown) tags

### Reliability Filter

| Signal | Weight |
|---|---|
| Verified purchase / hands-on shown on camera | +2 |
| Mentions trade-offs and limitations | +2 |
| Brand-sponsored / undisclosed partnership suspected | -3 |
| Generic specs copy without personal angle | -2 |
| Pure hype with no caveats | -2 |

Only sum-positive sources count toward the 5-source coverage.

## AI Search Prompt Templates

Use these templates with available web-search tools. Always run multiple variants per category.

### Discovery prompt

```
For category {X}, what are the top brands and models on the Chinese market in 2026?
Include: (1) the 3 most popular mainstream choices, (2) at least 2 niche or boutique options
that have strong word-of-mouth, (3) at least 1 high-end or alternative-tech-path option.
For each, note: country of origin, price tier, defining feature, common criticism.
```

### Pain-point prompt

```
What are the most common complaints from real users about {brand}-{model} in 2026?
Search 知乎 / 小红书 / B站 / 微博. Distinguish design flaws (hardware/structural) from
preference issues (taste/comfort). Cite source links.
```

### Comparable-case prompt

```
Find 3 companies / projects in the past 24 months that adopted {solution}.
For each: organization name, deployment scale, public outcome, lessons learned, source link.
```

### Alternative-path prompt

```
For the use case "{describe use case}", what alternative technical approaches exist
besides {default approach}? Compare on cost, complexity, maturity, and known risks.
```

## Mature Solution Benchmarking

Every recommendation must cite **2-3 mature reference implementations**. A "mature reference" satisfies all of:

- In production / use for >= 12 months
- Verified by a credible third party (news, case study, conference talk, or public list)
- Comparable in scale or complexity to the buyer's situation

Do not cite vendor-published case studies as the only reference — they are inherently biased.

## Anti-Mainstream-Bias Guardrails

When the recommended set is being assembled:

1. **Force include 1 niche-but-loved option.** Search "小众 + {category} + 推荐" or "{category} + boutique" specifically.
2. **Force include 1 high-end / alternative-tech option.** Even if the budget excludes it, the comparison forces the mainstream pick to justify its position.
3. **Reject the recommendation set if** all 3 picks come from the top-2 search-result brands. That is "first-page bias" — go deeper.

## Output Convention

In the operation `findings.md`, log a "Source coverage" subsection:

```
## Source coverage
- [x] Brand official site: vendor.com (2026-05-13)
- [x] Media / KOL: 小红书 笔记 link (2026-05-13)
- [x] B2B platform: 1688 link (2026-05-13)
- [x] Comparable case: 36kr article link (2026-05-12)
- [x] Industry report: 艾瑞 2025 报告 link
- 5/5 source types covered ✓
```

Mark unmet source types so reviewers can spot under-research.
