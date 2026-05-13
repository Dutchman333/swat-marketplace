---
name: procurement-deliverables
version: "1.0.0"
description: Self-contained HTML output templates for the four main procurement deliverables — market intelligence report, brand/model selection, supplier shortlist, and RFQ
---

# Procurement Deliverables

HTML output templates for the four standard deliverables. All templates are self-contained (inline CSS, no JS, no external assets) and Chinese-language.

## Use When

- Producing the final report at the end of an operation
- Standardizing layout across operations for the same captain

## Shared Layout Conventions

All four templates use:

- **Header band**: gradient (#0f172a → #1e3a8a → #0891b2), white title, project meta
- **Section card**: `background: #fff; border-radius: 10px; padding: 20px; margin-bottom: 16px; box-shadow: 0 1px 4px rgba(0,0,0,0.05);`
- **Color tags**:
  - 推荐 / 主选: `background: #dcfce7; color: #166534;`
  - 备选: `background: #fef3c7; color: #92400e;`
  - 否决 / 警示: `background: #fee2e2; color: #991b1b;`
- **Reliability stars**: ★★★★★ in `color: #fbbf24;`
- **FX rate notice**: `background: #fef9c3; border-left: 4px solid #f59e0b; padding: 10px 14px;`
- **Devil's Advocate box**: `background: #fef2f2; border-left: 4px solid #dc2626; padding: 12px 16px;`
- **Font stack**: `-apple-system, BlinkMacSystemFont, 'Segoe UI', 'PingFang SC', 'Microsoft YaHei', sans-serif`
- **Font size**: 15px body, 28px H1, 22px H2, 17px H3

## Template 1: 市场行情调研报告 (Market Intelligence Report)

Required sections:

1. **执行摘要** (executive summary card with 4-5 KPIs)
2. **市场价格区间** (price band card: low / median / high + source count)
3. **品牌格局** (brand landscape: mainstream / niche / high-end columns, each 3-5 brands with 1-line positioning)
4. **供应链结构** (where are factories, what's the import dependence, lead time norm)
5. **趋势与拐点** (price trend, tech trend, policy/tariff impact, 12-month outlook)
6. **采购建议** (timing, lot strategy, framework recommendation)
7. **风险与不确定性**
8. **证据清单** (evidence/INDEX.md summary inline)

## Template 2: 品牌/型号选型报告 (Brand & Model Selection)

Required sections:

1. **需求重述** (restate the use case to confirm understanding)
2. **候选清单** (must include >=1 mainstream + >=1 niche + >=1 high-end per anti-mainstream-bias rule)
3. **参数对比表** (spec matrix; highlight cells that fail the requirement in red)
4. **打分雷达** (radar table: 价格 / 性能 / 口碑 / 售后 / 适配度 — each 0-10)
5. **推荐结论** (主选 / 备选 / 高端对照, each with one-paragraph rationale)
6. **Devil's Advocate** (>= 3 reasons NOT to pick the 主选)
7. **采购建议** (where to buy, what to ask for, what to verify in person)
8. **证据清单**

## Template 3: 供应商对比+推荐名单 (Supplier Shortlist)

Required sections:

1. **采购需求摘要**
2. **候选供应商汇总表** (supplier name | category | quoted price | tax-inclusive? | MOQ | lead time | reliability star)
3. **多维评分卡** (5R scores per supplier — Right item / qty / price / time / source, each 0-5; flag any <=2)
4. **Kraljic 定位** (place this category in the 4-quadrant map; explicit strategy)
5. **背调结果汇总** (PASS / BORDERLINE / FAIL per supplier; link to evidence/dd-*.md)
6. **主选 / 备选 / 否决 决策**
7. **Devil's Advocate for 主选** (>= 3 reasons not to choose them)
8. **谈判杠杆建议** (top 3 leverages from negotiation library)
9. **风险与缓释**
10. **证据清单**

## Template 4: RFQ 拟稿+报价分析 (RFQ Template & Quotation Analysis)

### Part A — RFQ Template

Required fields:

1. 项目背景与采购方信息
2. 采购品名规格 (item / spec / quantity / packaging)
3. 交货要求 (delivery date / location / Incoterms)
4. 质量与验收标准 (acceptance criteria / sample requirement)
5. 商务条件 (payment terms / warranty / penalty / liability cap)
6. 报价格式要求 (must split tax-inclusive / tax-exclusive / VAT rate; line-item structure)
7. 提交方式与截止时间 (channel / deadline / contact)
8. 评分维度与权重 (price / quality / delivery / service / qualification — explicit weights)
9. 资质要求 (mandatory cert list)
10. 答疑窗口期 (Q&A schedule)

### Part B — Quotation Analysis (after responses arrive)

1. **报价收纳表** (each respondent: 报价含税 / 不含税 / 税率 / 交期 / 付款 / 异常项)
2. **价格分析** (median / range; flag low-outliers triggering low-price warning rule)
3. **资质对比** (Carter 10C scoring or pass-fail per cert)
4. **TCO 测算** (if equipment / multi-year — stacked cost across 3-5 year horizon)
5. **综合排名**
6. **谈判建议**
7. **下一步行动**

## Domestic Substitute Section (Conditional)

If the recommendation involves an imported product, add a **"国产替代对照"** section:

| 维度 | 进口推荐 | 国产替代 1 | 国产替代 2 |
|---|---|---|---|
| 单价 | ... | ... | ... |
| 关键参数差距 | baseline | gap | gap |
| 质量共识 | star | star | star |
| 售后 / 备件 | ... | ... | ... |
| 风险 | ... | ... | ... |

Conclude with one paragraph: when does the 国产替代 make sense; when stick with import.

## Code Skeleton (Python)

```python
HTML_HEAD = """<!DOCTYPE html>
<html lang="zh-CN"><head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>{title}</title>
<style>
body { font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'PingFang SC', 'Microsoft YaHei', sans-serif;
       margin: 0; padding: 0; color: #1a1a1a; background: #f6f9fc; line-height: 1.65; font-size: 15px; }
.container { max-width: 1200px; margin: 0 auto; padding: 24px 20px; }
header { background: linear-gradient(135deg, #0f172a 0%, #1e3a8a 60%, #0891b2 100%);
         color: #fff; padding: 36px 24px; margin-bottom: 24px; border-radius: 0 0 14px 14px;
         box-shadow: 0 4px 14px rgba(15,23,42,0.20); }
.section { background: #fff; padding: 24px; border-radius: 10px; margin-bottom: 20px;
           box-shadow: 0 1px 4px rgba(0,0,0,0.05); }
.tag-recommend { background: #dcfce7; color: #166534; padding: 3px 10px; border-radius: 4px; font-size: 13px; }
.tag-backup { background: #fef3c7; color: #92400e; padding: 3px 10px; border-radius: 4px; font-size: 13px; }
.tag-reject { background: #fee2e2; color: #991b1b; padding: 3px 10px; border-radius: 4px; font-size: 13px; }
.fx-notice { background: #fef9c3; border-left: 4px solid #f59e0b; padding: 10px 14px;
             border-radius: 4px; margin: 12px 0; }
.devils { background: #fef2f2; border-left: 4px solid #dc2626; padding: 12px 16px;
          border-radius: 4px; margin: 12px 0; }
.star { color: #fbbf24; }
table { width: 100%; border-collapse: collapse; margin: 12px 0; }
th, td { padding: 10px 12px; text-align: left; border-bottom: 1px solid #e5e7eb; }
th { background: #f1f5f9; font-weight: 600; }
h1 { margin: 0 0 8px 0; font-size: 28px; }
h2 { color: #1e3a8a; border-left: 4px solid #0891b2; padding: 4px 0 4px 12px;
     margin-top: 36px; font-size: 22px; }
h3 { color: #0891b2; margin-top: 24px; font-size: 17px; }
</style></head><body><div class="container">
"""

HTML_FOOT = "</div></body></html>"

def write_report(path, title, sections):
    with open(path, "w", encoding="utf-8") as f:
        f.write(HTML_HEAD.format(title=title))
        for s in sections:
            f.write(f'<section class="section">{s}</section>')
        f.write(HTML_FOOT)
```

Use this scaffold and fill in each section per the chosen template above.
