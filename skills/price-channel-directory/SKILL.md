---
name: price-channel-directory
version: "1.0.0"
description: Standardized list of Chinese price-discovery platforms with category-to-platform mapping and a selection decision tree
---

# Price Channel Directory

A maintained registry of platforms to query for price intelligence in Chinese procurement. Use this to satisfy the squad's "multi-source price evidence (>= 3)" rule.

## Use When

- The brief asks for market price benchmarking
- The brief asks for supplier sourcing
- A quote needs verification against market reference
- Comparing import vs domestic price for an imported item

## Channel Registry

### Consumer (B2C, end-user products)

| Platform | Strength | Notes |
|---|---|---|
| **JD (京东)** | Self-operated SKUs are most reliable; real invoice; fast logistics | **Always check 京东自营 first**; third-party sellers vary |
| **Tmall (天猫)** | Brand flagship stores; promo cycles | Watch for 旗舰店 vs 专卖店 vs 专营店 |
| **Taobao (淘宝)** | Long tail; small batches; lowest entry price | Quality variance — use only as price floor reference |
| **Pinduoduo (拼多多)** | Aggressive low pricing; group-buy mechanics | Treat as floor; verify spec carefully |
| **Suning (苏宁易购)** | Appliances, 3C; offline-online integration | Strong for white goods |

### B2B General

| Platform | Strength | Notes |
|---|---|---|
| **1688 (Alibaba)** | Largest B2B catalog; factory direct; MOQ visible | **Mandatory for any B2B brief**; cross-check with 京东工业 |
| **Huicong (慧聪)** | Industrial categories; older buyer base | Use for traditional industries (chemicals, machinery, building materials) |

### Cross-Border / Imports

| Platform | Strength | Notes |
|---|---|---|
| **Alibaba International (alibaba.com)** | Export prices; FOB / CIF visible | Use for understanding domestic factory export prices |
| **Made-in-China (made-in-china.com)** | Manufacturing-focused English catalog | Good for industrial OEM |
| **Global Sources (globalsources.com)** | HK-based; quality-vetted | Premium tier of Chinese exporters |
| **JD International (海囤全球)** | Bonded warehouse imports | Faster delivery for verified import goods |

### Industrial Supplies & Equipment (MRO)

| Platform | Strength | Notes |
|---|---|---|
| **西域 (xyznet.com.cn)** | Premium MRO; brand authorized | Good price baseline for industrial brands |
| **工品一号 (gongpin.com)** | Mid-tier MRO | Frequent promotions |
| **震坤行 (zkh.com)** | Largest MRO platform; full-stack | **Mandatory for industrial brief** |
| **JD 工业品 (industry.jd.com)** | JD ecosystem; invoice-friendly | Cross-reference with 震坤行 |

### Vertical Industry Specialists

| Platform | Domain | Notes |
|---|---|---|
| **找钢网 (zhaogang.com)** | Steel products | Live spot price |
| **摩贝 (molbase.com)** | Chemicals, fine chemicals, raw materials | API-grade and lab reagents |
| **必联网 (ebnew.com)** | Public bidding aggregator | Price-history mining for state procurement |
| **中国采购与招标网 (chinabidding.com.cn)** | Public bidding archives | Same purpose, complementary coverage |
| **慧亚 (huiya.com)** | Home goods, furniture, building materials | B2B home category |

### Used / B-Grade / Refurbished

| Platform | Notes |
|---|---|
| **闲鱼专业版 (xianyu.taobao.com)** | Pro / business sellers — verifies legitimacy |
| **JD 拍拍 (paipai.jd.com)** | JD-vetted second-hand |
| Category-specific second-hand sites | E.g., 旗鱼 for cars, 万表 for watches, 转转 for digital |

## Category-to-Channel Decision Tree

```
Is the item for personal / household use?
├─ YES → JD (self-op) + Tmall (flagship) + Taobao (price floor)
│         If high-end imported: + Alibaba International + JD 海囤全球
│
└─ NO → Is it MRO / industrial supplies?
         ├─ YES → 震坤行 + 西域 + 1688 工业品 + JD 工业品
         │
         └─ NO → Is it raw materials / commodities?
                  ├─ YES → use vertical specialist (找钢网 / 摩贝 / 慧亚)
                  │         + 1688 + Huicong
                  │
                  └─ NO → Is it a service or project?
                           ├─ YES → 必联网 + 中国采购与招标网 (history)
                           │         + direct supplier RFQ
                           │
                           └─ Default → 1688 + JD + Tmall (broad scan)
```

## Mandatory Coverage Rule

For any brief, the squad must query **at least 3 platforms** spanning **at least 2 channel groups** above. Single-channel pricing is forbidden.

## Capture Conventions

For each price quoted in the report, store the following in `evidence/`:

```
evidence/
├── jd_<sku-id>_<YYYYMMDD>.png        screenshot of the SKU page
├── 1688_<offer-id>_<YYYYMMDD>.png
├── ...
└── INDEX.md                           manifest with URL, capture timestamp, captured by
```

The INDEX.md format:

```
| File | Source URL | Captured | Notes |
|------|-----------|----------|-------|
| jd_100012345_20260513.png | https://item.jd.com/... | 2026-05-13 14:33 CST | 京东自营，含税含运 |
```

## Platform Health Check

When a platform listed above is unreachable or significantly changed (interface, geo-block, account requirement), note it in the operation `findings.md` so the directory can be updated in a future skill version.
