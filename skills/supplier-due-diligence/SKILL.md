---
name: supplier-due-diligence
version: "1.0.0"
description: Standardized supplier background investigation — 30 checkpoints across 5 categories with red-flag thresholds and Chinese registry sources
---

# Supplier Due Diligence

A reusable checklist for evaluating Chinese supplier credibility. Each item specifies the lookup source and the red-flag threshold.

## Use When

- Recommending a primary supplier
- Evaluating a quotation from an unfamiliar party
- Comparing 3+ suppliers in a shortlist
- Background-checking a sales lead

## Five Categories

### 1. Business Registration (workmanship & longevity)

Source: 国家企业信用信息公示系统 (gsxt.gov.cn) | 天眼查 (tianyancha.com) | 启信宝 (qixin.com)

| # | Item | Red flag |
|---|---|---|
| 1.1 | Registered capital (注册资本) | < 1M CNY for B2B / 100K for individual seller |
| 1.2 | Paid-in capital (实缴资本) | Massive gap vs registered (10x+ shortfall) |
| 1.3 | Established date (成立年限) | < 2 years for materials / equipment supplier |
| 1.4 | Business scope (经营范围) | Quoted product not in scope |
| 1.5 | Legal representative (法定代表人) | Holds positions in 5+ companies (proxy operator) |
| 1.6 | Shareholders (股东信息) | Single shareholder + frequent change history |
| 1.7 | Change history (变更记录) | Frequent name / address / capital changes (3+ in 24 months) |
| 1.8 | Branches / subsidiaries (分支机构) | None vs the scale claimed |

### 2. Financial Health (going concern)

Source: Annual report disclosures (年报) | tax credit rating (纳税信用等级) | bank credit references

| # | Item | Red flag |
|---|---|---|
| 2.1 | Annual revenue trend | Declining 3 years; or undisclosed |
| 2.2 | Taxpayer status (纳税人身份) | Small-scale claiming large-batch capability |
| 2.3 | Tax credit rating | C or D level (downgraded by 税务局) |
| 2.4 | Social insurance headcount (社保人数) | < 5 vs claimed factory size; or N/A |
| 2.5 | Bank account count | None disclosed; or only individual accounts |

### 3. Qualifications (capability)

Source: Industry-specific certifying bodies | factory audit reports | brand authorization letters

| # | Item | Red flag |
|---|---|---|
| 3.1 | ISO 9001 (quality management) | Expired or unverifiable certificate number |
| 3.2 | Industry licenses | Missing required license (food / medical / fire / electronics / etc.) |
| 3.3 | Brand authorization | Sells brand X without authorization letter |
| 3.4 | Patents / trademarks | Trademark squatting indicators |
| 3.5 | Product certifications | CCC / CE / FCC missing for regulated categories |
| 3.6 | Factory or office address | Virtual office / shared address / google maps shows storefront only |
| 3.7 | Production / service capacity | Cannot demonstrate equipment list, headcount, or output |

### 4. Case History & Reputation (track record)

Source: Supplier portfolio | customer references | online complaints | social media

| # | Item | Red flag |
|---|---|---|
| 4.1 | Named customer references | All large-name claims unverifiable |
| 4.2 | Project showcase with proof | Generic stock images for "case studies" |
| 4.3 | Online review consensus | Mostly negative on 知乎 / 黑猫 / 微博 |
| 4.4 | Industry awards or recognition | Suspect "国家级" titles unverifiable in 国家奖项数据库 |
| 4.5 | Years of relationship with anchor customers | None stable past 3 years |

### 5. Risk Signals (defensive checks)

Source: 中国裁判文书网 (wenshu.court.gov.cn) | 信用中国 (creditchina.gov.cn) | environmental bureau public lists

| # | Item | Red flag |
|---|---|---|
| 5.1 | Lawsuits as defendant (法院判决) | 3+ contract disputes in 24 months |
| 5.2 | Executions (被执行人) | Listed as 被执行人 / 限制高消费 |
| 5.3 | Tax irregularities (税务异常) | Listed as 重大税收违法 |
| 5.4 | Operating status (经营异常) | Listed as 经营异常 (failed annual report, address unverifiable, etc.) |
| 5.5 | Equity freezes (股权冻结) | Active equity freeze on shareholders |
| 5.6 | Environmental violations (环保处罚) | Listed in 环境违法企业名单 within 36 months |
| 5.7 | Sanctioned / blacklist exposure | On 失信被执行人 list |

## Scoring & Decision

For each shortlisted supplier, fill the 30-row table; assign:

- **PASS** = all "must-have" items clean (item 1.4 in scope, item 2.3 not D-grade, item 5.1/5.2/5.3 clean)
- **BORDERLINE** = 1-2 minor red flags, mitigatable via deposit / warranty / dual source
- **FAIL** = any "must-have" red flag, or 3+ minor red flags

## Completeness Flag

If any of the 30 items returns "无法查询" / "信息缺失" — **the report must explicitly state**:

> "本次背调缺失 N 项关键信息（列出哪几项），不构成完整尽调，建议在签合同前补充：(1) 直接索取证照原件，(2) 第三方实地核查，(3) 银行资信证明。"

This protects the buyer from making a decision based on partial information.

## Output Convention

Insert a "供应商背调汇总" table in the report with: 供应商名称 | PASS/BORDERLINE/FAIL | 关键红旗（如有）| 缺失信息项数 | 建议措施.

Each supplier card should link to a per-supplier evidence file in `evidence/dd-{supplier-name}.md`.
