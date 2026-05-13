---
name: travel-frameworks
version: "1.0.0"
description: Travel planning methodology library — pacing rules, budgeting templates, destination intelligence framework, and family-vs-couple-vs-solo scenario adaptation
---

# Travel Frameworks

Methodology and decision frameworks for travel planning. Category-agnostic but scenario-aware.

## Use When

- Designing a multi-day itinerary
- Sanity-checking a proposed pace
- Building a budget breakdown
- Researching a destination's suitability

## The Two-Scenario Pacing Model

### Scenario 1: Family with toddler (3-year-old + grandparents / nanny optional)

| Constraint | Rule |
|---|---|
| Days per destination | >= 3 nights (avoid 1-night hops) |
| Daily activity blocks | <= 2 (one morning, one afternoon; nap window 12:30-15:00) |
| Single-leg car / transit | <= 2 hours |
| Walking per day | <= 6 km, prefer stroller-friendly paths |
| Restaurant choice | Reservation-required + kid-friendly + < 30 min travel |
| Day-2 of arrival | Light schedule (jet-lag / fatigue buffer) |
| Buffer day every | 4 days minimum |

### Scenario 2: Couple or solo

| Constraint | Rule |
|---|---|
| Days per destination | >= 2 nights for cities, >= 3 for nature |
| Daily activity blocks | 3-4 acceptable |
| Single-leg car / transit | <= 4 hours; longer OK with scenic value |
| Walking per day | <= 15 km |
| Restaurant choice | Mix of 1-2 fine-dining + 1-2 local exploration |
| Day-2 of arrival | Can start full-pace if no time-zone gap > 6h |
| Buffer day every | 5-6 days |

## Destination Intelligence Checklist

Before any destination recommendation, research and surface:

| Dimension | What to find |
|---|---|
| **Climate window** | Best months, monsoon / typhoon / heatwave / extreme cold periods, current month forecast |
| **Safety baseline** | 中国领事服务网 advisory level, US/UK travel advisory, common scams, neighborhoods to avoid |
| **Kid-friendliness** (Scenario 1) | Stroller infrastructure, baby food availability, hospital network, kid attractions density |
| **Cultural notes** | Tipping norm, dress code (religious sites), language barrier severity, photography restrictions |
| **Connectivity** | Visa-free / visa-on-arrival / visa-required + processing time |
| **Cost level** | Approx daily spend per scenario (food + transport + entry, ex-hotel) |
| **Logistics** | Best airports, intra-city transport quality, English-friendliness of taxis |
| **Hidden costs** | Tourist tax, museum reservation lottery (e.g. Vatican, Alhambra), peak surcharges |

Dump the findings into a "目的地情报" section before itinerary design.

## Budget Breakdown Template

```
| 类别 | 单日 / 单次 | 天数 / 次数 | 小计 (CNY) | 备注 |
|------|------------|-------------|------------|------|
| 国际机票 (4 大 1 小) | ¥X | 1 | ¥X | 五星航司经济舱 |
| 酒店 (套房 / 家庭房) | ¥X | N | ¥X | IHG 大使福利已应用 |
| 当地交通 | ¥X | N | ¥X | 含接送机 + 包车 / 租车 / 公共 |
| 餐饮 | ¥X | N | ¥X | 含 1-2 顿米其林 |
| 门票 / 活动 | ¥X | N | ¥X |  |
| 育婴师机酒 | ¥X | N | ¥X | 仅 Scenario 1 |
| 签证 / 保险 | ¥X | 1 | ¥X |  |
| 购物预留 | ¥X | 1 | ¥X | 可选 |
| 应急储备 (10%) | — | — | ¥X | 行李 / 医疗 / 改签 |
| **合计** | — | — | **¥X** |  |
```

## Itinerary Day Block Template

```
## Day N · YYYY-MM-DD (周X)
**主题**: <e.g. 抵达 + 适应 / 城市探索 / 自然与休闲>
**酒店**: <name> · 入住时间 <hh:mm> · 退房 <hh:mm>

### 上午 (09:00 - 12:00)
- POI / 活动: <name> | 童友 ★N/5 | 入场 ¥X | 时长 90 min | 链接
- 交通: <模式> · <时长> · ¥X

### 午餐 (12:00 - 13:30)
- 餐厅: <name> | 童友 ★N/5 | 人均 ¥X | 必点 / 提示

### 下午 (15:30 - 18:00)   <!-- Scenario 1: 午休 13:30-15:30 -->
- 活动 / POI ...

### 晚餐 (19:00 - 20:30)
- 餐厅 ...

### 夜间 (可选)
- 散步 / 看展 / 早休息
```

## Off-Peak Detection Rules

Mark the following date windows as **PEAK** with explicit warnings:

| Period | Why peak | Alternative window suggestion |
|---|---|---|
| 春节 (除夕 - 初七) | 国内全面峰值 + 海外华人聚集地 | 春节后 3 周 / 春节前 2 周 |
| 清明 / 端午 / 中秋 / 国庆 | 国内峰值 | 节后 2 周 |
| 7 月中 - 8 月底 | 学校暑假 + 全球高峰 | 6 月 / 9 月 |
| 1 月下 - 2 月初 (寒假) | 中国学校寒假 | 12 月 / 3 月 |
| 元旦 / 圣诞 | 欧美高峰 + 华人圣诞旅游 | 11 月 / 1 月中 |
| 樱花 / 红叶 / 极光高峰 | 目的地特定峰值 | 看具体目的地 |

For each detected peak overlap: insert a notice block with **crowd level (★1-5)**, **price uplift estimate (% vs off-peak)**, and **2 alternative dates** that respect the operator's flexible schedule.

## Output Convention

Every framework reference in the report must show: which framework, the inputs, the derived recommendation. Never use a framework as decoration.
