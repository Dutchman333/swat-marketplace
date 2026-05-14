---
name: personal-company-profile
version: "1.0.0"
description: Embedded company-and-personal legal profile of the squad operator — group structure, employee mix, labor history, certifications, family composition, asset profile, succession-track context, and scenario detection rules. Customize this file with your own values before first use.
---

# Personal & Company Legal Profile  &nbsp;<sub>· Template version</sub>

> **🔧 SETUP REQUIRED.** This skill is the **personal config** of the `chinese-legal-advisor` squad. Before your first run, **edit every section below** marked with `<TODO: ...>` to fit your situation. The squad will read this file at the start of every operation and apply your preferences automatically.
>
> **Privacy note:** This file lives in your local SWAT installation. **Do not commit your filled-in version back to a public repo** unless you've reviewed every line for PII you're comfortable sharing.

This skill encodes the operator's company-group + personal legal profile. The chinese-legal-advisor squad must read this skill **first** in every operation and apply the profile unless the brief explicitly overrides specific items.

## How to Apply

1. Load this profile at the start of every operation.
2. Use the **Scenario Detection** rules below to pick Scenario 1 (Company) vs Scenario 2 (Personal) based on the brief's wording.
3. Apply preferences automatically — never ask the operator to re-confirm what's already encoded here.
4. The brief can override any item; when it does, log the override in `findings.md` per the override convention at the bottom of this file.
5. Per Hard Rule 7 — every PII string in this profile must be **desensitized** when it appears in a `report.html` (use `[公司A]` / `[父亲]` / `[配偶]` / etc.). Raw values are preserved here for the operator-facing analysis only.

---

## Group Structure (集团 — Scenario 1)  &nbsp;<sub><TODO: 按你公司情况填></sub>

### Position
- **Operator's role**: `<TODO: e.g., 总经理 / 总经理助理 / HR 总监 / 法务 / 创始人 / 股东 / 员工 / 顾问>` — `<TODO: e.g., succession track / professional manager / outside counsel>`
- **Operator's age bracket / generation**: `<TODO: e.g., 接班人 / 创一代 / 职业经理人 / 中层>`

### Companies (1 to N companies in operator's group)

| Company | Headcount | Industry / Sector | Notes |
|---|---|---|---|
| `<TODO: 公司全名 1>` | `<TODO: 员工数>` | `<TODO: 行业>` | `<TODO: 设备/特色/客户>` |
| `<TODO: 公司全名 2>` (if applicable) | `<TODO>` | `<TODO>` | `<TODO>` |
| `<TODO: ...>` | `<TODO>` | `<TODO>` | `<TODO>` |

**Total headcount**: `<TODO: 总员工数;影响适用劳动法的细化档(<10/10-50/50-200/200+);200+ 公司必须建工会、必须订集体合同 等)>`

### Industry Profile

- **Industry**: `<TODO: 制造 / 印染 / 化工 / 电商 / 服务 / 金融 / 互联网 / 教培 / 餐饮 / 医疗 / 房地产 / 物流 / 等>`
- **Region**: `<TODO: 你公司主要经营地;影响劳动仲裁院 / 法院 / 行政复议 等管辖>`
- **Certifications**: `<TODO: ISO9001 / OEKO-TEX / GRS / 高新企业 / 等;关系合规背景 + 数据治理基线>`
- **Distinguishing features**: `<TODO: 你公司在合规 / 资质 / 客户结构上的特殊点>`

### Labor / HR Profile

- **Employment model**: `<TODO: 全职为主 / 派遣为主 / 灵活用工 / 平台合作 / etc.>`
- **Returning retirees** (退休返聘): `<TODO: YES / NO;若 YES,人数与岗位>`
- **Interns / temp workers**: `<TODO: 极少 / 季节性大量 / 常态>`
- **Foreign employees**: `<TODO: YES / NO;若 YES,签证类型>`
- **Union (工会)**: `<TODO: EXISTS / NOT EXISTS;若 EXISTS,实际权力 强 / 中 / 弱>`

### Legal History (Recurring Use Cases)

- **Labor arbitration (劳动仲裁)**: `<TODO: 频次 — 每年 N 起 / 偶发 / 从未;主要类型 — 经济补偿 / 加班费 / 解除异议 / 三期异议 / 工伤补偿 / 等>`
- **Workplace injuries (工伤事故)**: `<TODO: 频次;高发岗位 — 化学品 / 高温 / 设备 / 高空 / 等>`
- **Compliance posture**: `<TODO: 已有/未有的合规底子 — 数据治理 / 化学品管理 / 环保 / 安全生产 / etc.>`
- **Cross-border**: `<TODO: 是否有海外客户 / 海外股东 / 跨境数据 / 跨境员工>`

### Asset Profile (Group)

- `<TODO: 主要资产种类 — 厂房 / 设备 / 商标 / 专利 / 客户名单 / 软件 / 库存 / 应收 / 等>`
- `<TODO: 设备 / 不动产 抵押情况 — 自查后填>`
- `<TODO: 商业秘密 高价值 — 客户名单 / 工艺 / 配方 / 算法 / 等;强弱>`

---

## Personal Profile (Scenario 2 — Operator + Family)  &nbsp;<sub><TODO: 按你家庭情况填></sub>

### Marital + Family Status

- **Marital status**: `<TODO: married / single / divorced / widowed>`
- **Spouse**: `<TODO: alive / deceased / divorced;若 alive,是否双方均同意财产分割安排>`
- **Children**: `<TODO: 几个;年龄;特殊需要;监护问题>`
- **Operator's parents**:
  - Father: `<TODO: alive / deceased;若 alive,健康状况;是否参与企业经营;是否已立遗嘱>`
  - Mother: `<TODO: 同上>`
- **Operator's siblings**: `<TODO: 数量;关系;是否参与家族企业;是否有财产纠纷史 — 影响 法定继承顺位的份额计算>`

### Asset Profile (Operator's Personal)

| Item | Status |
|---|---|
| 房产 | `<TODO: NONE / OWNED;若 OWNED,数量 / 地点 / 产权登记人 / 是否有按揭>` |
| 投资 | `<TODO: NONE / YES;类型:股票/基金/私募/数字资产/海外资产/等>` |
| 担保 (个人为他人提供) | `<TODO: NONE 推荐保持 / EXISTS;若 EXISTS,被担保人 / 金额 / 条件>` |
| 集团 / 公司 持股 | `<TODO: 公司全名 + % + 类别(自然人股 / 信托持股);影响个人财产隔离 + 婚姻共同财产判定>` |
| 离岸 / 跨境 资产 | `<TODO: 影响 PIPL + 个税 + 跨境继承复杂度;Common Reporting Standard 申报义务>` |

### Personal-Side Recurring Legal Concerns

- `<TODO: 你高频关注的个人法务领域,如:婚姻家庭 / 继承 / 物业 / 消费维权 / 借贷 / 交通事故 / 医疗 / 房产交易 / 知识产权 / 等>`

---

## Scenario Detection Rules

| Brief contains | → Scenario |
|---|---|
| 公司 / 员工 / HR / 仲裁 / 工伤 / 合同 / 客户 / 厂里 / 车间 / 集团 / 业务 / 部门 / 岗位 + 行业关键词(`<TODO: 你行业的标志词>`) | Scenario 1 (Company) |
| 我自己 / 我老婆 / 我家 / 我女儿 / 我儿子 / 父亲 / 母亲 / 继承 / 婚姻 / 离婚 / 房产 / 投资 / 借贷 / 消费 / 物业 / 遗嘱 / 配偶 / 个人 / 自己 / 接班 / 股权 (个人持股 维度) | Scenario 2 (Personal) |
| 接班 / 股权 传承 / 父亲 给我 公司 / 集团 治理 接班 | **Both** — apply both profiles; report should explicitly distinguish 公司层 (Scenario 1) vs 个人层 (Scenario 2) sections |
| Mixed / unclear signals | **Default `<TODO: Scenario 1 or 2 — pick your higher-frequency stream>`**; surface assumption in report's Assumptions block |

---

## Default Reporting Conventions Tied to This Profile

When generating reports for this operator:

- **Region**: `<TODO: 你公司经营地;主要管辖 — 仲裁院 / 法院 / 行政复议 / 工伤认定 部门>`
- **Industry baseline**: `<TODO: 行业典型法规触发点 — 化学品 / 高温 / 高湿 / 数据 / 食品安全 / 等>`
- **Currency**: CNY
- **Language**: Chinese (per Hard Rule 10) — even if operator's brief is in English
- **Lawyer-recommendation banner trigger**: 公司规模 / 工伤累计风险 / 跨境业务 决定 banner 触发频次 — `<TODO: 你公司情况>`
- **Cross-border dimension**: `<TODO: 是否常触发 PIPL + DSL + 跨境数据评估 / 跨境合同审查;default path 推荐>`
- **Personal-side 高敏感**: `<TODO: 你最关注的 1-3 个个人法务点>`

---

## Specific Risk Watch-List (Pre-flagged)  &nbsp;<sub><TODO: 按你情况裁剪;以下为示例></sub>

These are the ongoing risks the squad should proactively check against in any operation. **EXAMPLE list below — replace with your own.**

| Watch item | Source | Triggered when |
|---|---|---|
| 公司法 5 年 实缴 调整 | 新公司法 第47条 | Any brief touching 集团 资本 / 股东 / 章程 |
| 父亲 / 母亲 遗嘱 状态 — 已立 / 未立? 公证 / 律师代书 / 自书? | 民法典 继承编 第1133-1144条 | Any brief touching 接班 / 父母 健康 / 家族财产 |
| 操作员 自己 遗嘱 — 已立 / 未立? | 民法典 继承编 + Case D in inheritance-book.md | Any brief touching 婚姻 / 子女 / 操作员 自身 资产 |
| 婚姻 财产协议 (操作员 + 配偶) — 已签 / 未签? 公证? | 民法典 第1065条 | Any brief touching 重大资产 / 公司股权变化 |
| 工伤 应急 SOP — 是否 24 小时内 启动 单位 申报? | 工伤条例 第17条第1款 (单位 30 日 限) | Any 新发 工伤 brief |
| 离职 员工 商业秘密 风险 — NDA + 同业限制 + 数据回收? | 反不正当竞争法 第9条 + 劳动合同法 第23-24条 | 任何 关键 员工 (技术 / 销售 / 高管) 离职 brief |
| 客户 个人信息 跨境 — 标准合同 备案? | PIPL 第38-43条 | 涉外 客户 数据 跨境 任何 brief |
| 集团 关联交易 决策留痕 + 关联董事 回避? | 公司法 第180-191条 | 关联 交易 / 利益输送 brief |
| 三期 / 工伤 / 医疗期员工 解除 — 第42条 hard ban | 劳动合同法 第42条 | 任何 拟 解除 brief |
| 高温 津贴 + 加班费 基数 + 最低工资 — 月度 自查 | 各地 工资支付条例 + 劳部 [1994] 489 号 | 任何 工资 / 仲裁 brief |

`<TODO: 加你自己关心的 watch items;删掉不适用的>`

---

## Override Convention

If a specific brief overrides any item above (e.g., "operator divorced last year — joint-property profile no longer applies", "this brief is about a different family member, not operator's daughter"), log it in the operation `findings.md` under "Profile overrides this run":

```
## Profile overrides this run
- Brief override: <override item>; reason: <why>
- Effective profile: <what we used in lieu of profile default>
```

This keeps the audit trail clean and lets the squad maintain consistent default behavior across operations.

---

## Profile Maintenance

Update this file when any of these changes occur:
- Operator's marital status changes
- Operator's children change (additional birth, adoption)
- Operator's parents' status changes (illness, death — affects succession urgency)
- Operator's group restructures (new company, M&A, divestiture, headcount change > ±20%)
- Operator's industry certification status changes
- Operator acquires / sells significant property / investment / business
- Operator takes on / removes 担保 (changes risk profile)
- Operator's region of operation changes

Each material update should bump this skill's `version:` (e.g., 1.0.0 → 1.1.0 for added sections, 1.0.0 → 1.0.1 for value updates).

---

## 📝 First-Run Checklist

Before your first `chinese-legal-advisor` operation:

- [ ] Group Structure section filled (1 to N companies + headcount + industry + region)
- [ ] Labor / HR Profile filled (employment model + union + legal history)
- [ ] Personal Profile filled (marital status + children + parents + assets)
- [ ] Scenario Detection rules adjusted (industry-specific keywords)
- [ ] Default Reporting Conventions tied to your jurisdiction
- [ ] Specific Risk Watch-List trimmed and customized
- [ ] This file is **NOT** committed back to any public repo

Once filled, this profile drives every operation report — the more accurate the profile, the more useful the recommendations.
