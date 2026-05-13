---
name: travel-deliverables
version: "1.0.0"
description: Self-contained HTML output templates for the six main travel deliverables — destination comparison, hotel comparison, flight comparison, day-by-day itinerary, budget breakdown, and visa advisory
---

# Travel Deliverables

HTML output templates for the six standard travel deliverables. All templates are self-contained (inline CSS, no JS) and Chinese-language.

## Use When

- Producing the final report at the end of an operation
- Standardizing layout across operations

## Shared Layout Conventions

All templates use:

- **Header band**: gradient (#0c4a6e → #0e7490 → #14b8a6), white title, project meta, optional notice strip
- **Section card**: `background: #fff; border-radius: 10px; padding: 20px; margin-bottom: 16px; box-shadow: 0 1px 4px rgba(0,0,0,0.05);`
- **Color tags**:
  - 推荐 / 主选: `background: #dcfce7; color: #166534;`
  - 备选: `background: #fef3c7; color: #92400e;`
  - 否决 / 警示: `background: #fee2e2; color: #991b1b;`
- **Kid-friendly stars** (Scenario 1): ★★★★★ in `color: #fb923c;` (warm orange — distinct from reliability gold)
- **Reliability stars**: ★★★★★ in `color: #fbbf24;`
- **FX rate notice**: `background: #fef9c3; border-left: 4px solid #f59e0b; padding: 10px 14px;`
- **Visa notice / off-peak warning**: `background: #fef2f2; border-left: 4px solid #dc2626; padding: 12px 16px;`
- **Loyalty perk badge**: `background: #ede9fe; color: #6d28d9; padding: 3px 10px; border-radius: 4px; font-size: 13px;`
- **Devil's Advocate box**: `background: #fff7ed; border-left: 4px solid #ea580c; padding: 12px 16px;`
- **Savings tip / Pitfall box**: `background: #ecfeff; border-left: 4px solid #06b6d4;` for savings; `background: #fef2f2; border-left: 4px solid #dc2626;` for pitfalls
- **Font stack**: `-apple-system, BlinkMacSystemFont, 'Segoe UI', 'PingFang SC', 'Microsoft YaHei', sans-serif`
- **Font size**: 15px body, 28px H1, 22px H2, 17px H3

## Top-of-Report Notice Bar

Always render at the top (when applicable):

```
[ 签证 ] 申根签证需提前 X 周办理 — 推荐 6 月底前递交  (red border)
[ 错峰 ] 当前日期落在 Y 高峰，价格预估上浮 N% — 见替代窗口  (amber border)
[ 安全 ] 目的地当前安全等级 X — Z 区域避开  (gray border)
```

## Template 1: 目的地对比 + 推荐 (Destination Comparison)

Sections:

1. **任务理解** (restate the brief in one paragraph + scenario detection)
2. **候选目的地总览** (3-6 destinations as cards: country/city, season fit, suitable scenario, headline rationale)
3. **多维评分对比** (table: 安全 / 童友 / 季节适配 / 文化深度 / 交通便利 / 性价比 / 签证难度 — each 0-10)
4. **气候与最佳时段** (per destination: best months, current month forecast, conditions)
5. **签证 + 安全速查**
6. **建议组合** (主选 + 备选 + 极端备选 — each with 1 paragraph)
7. **Devil's Advocate** for the 主选
8. **节省点 (3 条) + 潜在踑坑 (3 条)**

## Template 2: 酒店对比 + 主选 (Hotel Comparison)

Sections:

1. **入住条件摘要** (dates, headcount, scenario, area requested)
2. **候选酒店总览** (3-6 hotels as cards: brand affiliation, room type, neighborhood, kid-friendly ★, loyalty perk badge if applicable)
3. **多平台比价表** (per hotel — at least 5 source rows: 携程 / 飞猪 / Booking / Agoda / Trip.com / 直订 / etc.)
4. **会员权益对比** (IHG Ambassador / Marriott Gold benefit dollar value calculation)
5. **房型与设施详图** (room amenities, hotel amenities, kid amenities, view, breakfast, pool, lounge)
6. **位置 + 周边 + 交通** (POI distance map description, transit time to airport / city center)
7. **主选 / 备选 / 否决 决策**
8. **Devil's Advocate** for the 主选
9. **节省点 + 潜在踑坑**

## Template 3: 机票方案对比 (Flight Comparison)

Sections:

1. **行程要求摘要** (origin, destination, dates, headcount, cabin)
2. **航司筛选说明** (5-star preferred filter applied; mainland-carrier default-avoid; any deviations declared)
3. **候选航班总览** (3-6 options as cards: airline, flight numbers, route, total time, layovers, cabin, total CNY)
4. **多平台比价表** (per option — at least 3 source rows: Skyscanner + Google Flights + 航司直订)
5. **机型 + 服务对比** (aircraft, seat product, lounge, meal, baggage, on-time stats)
6. **里程 / 升舱选项** (mileage earn estimate, paid upgrade availability, points cost if redeemable)
7. **主选 / 备选 / 否决 决策**
8. **Devil's Advocate** for the 主选
9. **节省点 + 潜在踑坑**

## Template 4: Day-by-Day 完整行程 (Itinerary)

Sections:

1. **行程概览** (dates, total days, scenario, headcount, route map text, total budget)
2. **签证 + 安全 + 错峰 顶部 notice**
3. **机票方案** (summary card linking to fuller flight comparison or embedded mini-version)
4. **酒店方案** (summary cards per night-block linking to fuller hotel comparison)
5. **Day N · YYYY-MM-DD** blocks (use the day-block template from travel-frameworks: 上午 / 午餐 / 下午 / 晚餐 / 夜间; each POI / restaurant has kid-friendly ★ when Scenario 1)
6. **预算明细表** (full breakdown — see Template 5)
7. **节省点 + 潜在踑坑**
8. **应急联系信息** (operator-side: insurance, embassy, hotel concierge phone format reminder)

## Template 5: 预算明细 (Budget Breakdown)

Sections:

1. **总预算与人均**
2. **分类汇总表** (机票 / 酒店 / 当地交通 / 餐饮 / 门票 / 育婴师 / 签证保险 / 购物预留 / 应急 10%)
3. **每日预算曲线** (text-based: which days are spend-heavy and why)
4. **会员权益抵扣** (IHG Ambassador free breakfast value, Marriott Gold late checkout, BOGO redemption — quantified)
5. **节省点** (3 specific actions with quantified savings)
6. **可上调项** (where to spend more for noticeable upgrade — e.g., +¥X for premium economy on 12h leg)

## Template 6: 签证攻略 (Visa Advisory)

Sections:

1. **目的地签证类型与有效期**
2. **申请通道对比** (consulate vs VFS vs e-visa; processing time worst-case)
3. **材料清单** (docs needed; for Schengen, the photo requirement, insurance min coverage, financial proof, itinerary, hotel reservation, etc.)
4. **递交时间表** (apply-by date relative to departure; with buffer)
5. **拒签风险与应对** (common rejection reasons + mitigation)
6. **多次签证策略** (when to opt for multi-entry, how to phrase the itinerary)
7. **儿童签证特殊要求** (if Scenario 1)

## Code Skeleton (Python)

```python
HTML_HEAD = """<!DOCTYPE html>
<html lang="zh-CN"><head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>{title}</title>
<style>
body { font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'PingFang SC', 'Microsoft YaHei', sans-serif;
       margin: 0; padding: 0; color: #1a1a1a; background: #f0f9ff; line-height: 1.65; font-size: 15px; }
.container { max-width: 1200px; margin: 0 auto; padding: 24px 20px; }
header { background: linear-gradient(135deg, #0c4a6e 0%, #0e7490 60%, #14b8a6 100%);
         color: #fff; padding: 36px 24px; margin-bottom: 24px; border-radius: 0 0 14px 14px;
         box-shadow: 0 4px 14px rgba(12,74,110,0.20); }
.section { background: #fff; padding: 24px; border-radius: 10px; margin-bottom: 20px;
           box-shadow: 0 1px 4px rgba(0,0,0,0.05); }
.tag-recommend { background: #dcfce7; color: #166534; padding: 3px 10px; border-radius: 4px; font-size: 13px; }
.tag-backup { background: #fef3c7; color: #92400e; padding: 3px 10px; border-radius: 4px; font-size: 13px; }
.tag-reject { background: #fee2e2; color: #991b1b; padding: 3px 10px; border-radius: 4px; font-size: 13px; }
.tag-loyalty { background: #ede9fe; color: #6d28d9; padding: 3px 10px; border-radius: 4px; font-size: 13px; }
.kid-star { color: #fb923c; }
.rel-star { color: #fbbf24; }
.fx-notice { background: #fef9c3; border-left: 4px solid #f59e0b; padding: 10px 14px; border-radius: 4px; margin: 12px 0; }
.visa-notice { background: #fef2f2; border-left: 4px solid #dc2626; padding: 12px 16px; border-radius: 4px; margin: 12px 0; }
.peak-notice { background: #fffbeb; border-left: 4px solid #f59e0b; padding: 12px 16px; border-radius: 4px; margin: 12px 0; }
.devils { background: #fff7ed; border-left: 4px solid #ea580c; padding: 12px 16px; border-radius: 4px; margin: 12px 0; }
.savings { background: #ecfeff; border-left: 4px solid #06b6d4; padding: 12px 16px; border-radius: 4px; margin: 12px 0; }
.pitfalls { background: #fef2f2; border-left: 4px solid #dc2626; padding: 12px 16px; border-radius: 4px; margin: 12px 0; }
.day-block { background: #f8fafc; border-radius: 10px; padding: 16px 20px; margin-bottom: 14px; border-left: 4px solid #0e7490; }
table { width: 100%; border-collapse: collapse; margin: 12px 0; }
th, td { padding: 10px 12px; text-align: left; border-bottom: 1px solid #e5e7eb; }
th { background: #f1f5f9; font-weight: 600; }
h1 { margin: 0 0 8px 0; font-size: 28px; }
h2 { color: #0c4a6e; border-left: 4px solid #14b8a6; padding: 4px 0 4px 12px; margin-top: 36px; font-size: 22px; }
h3 { color: #0e7490; margin-top: 24px; font-size: 17px; }
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
