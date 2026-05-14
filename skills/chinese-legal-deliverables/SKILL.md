---
name: chinese-legal-deliverables
version: "1.0.0"
description: Self-contained HTML output templates for the six main Chinese-legal deliverables — Q&A, contract review, document drafting, risk assessment, case synthesis, legislation brief — with shared visual conventions and PII desensitization helper
---

# Chinese Legal Deliverables

HTML output templates for the six standard deliverables produced by chinese-legal-advisor. All templates are self-contained (inline CSS, no JS, no external assets) and Chinese-language (per Hard Rule 10).

## Use When

- Producing the final report at the end of an operation
- Standardizing layout across operations for the same operator
- Implementing PII desensitization (Hard Rule 7) consistently

## Shared Visual Conventions

All six templates use the following inline CSS conventions. Copy these into the `<style>` block of every report.

### Color Palette — Legal Blue + Risk Codes

```
/* Header band — gradient */
background: linear-gradient(135deg, #1a365d 0%, #2c5282 50%, #2b6cb0 100%);
color: #ffffff;

/* Section card */
background: #fff;
border-radius: 10px;
padding: 20px;
margin-bottom: 16px;
box-shadow: 0 1px 4px rgba(0, 0, 0, 0.06);

/* Risk color codes (per Hard Rule + risk-matrix framework) */
.risk-low,    .tag-green   { background: #dcfce7; color: #166534; padding: 2px 8px; border-radius: 4px; font-size: 13px; }
.risk-mid,    .tag-amber   { background: #fef3c7; color: #92400e; padding: 2px 8px; border-radius: 4px; font-size: 13px; }
.risk-high,   .tag-red     { background: #fee2e2; color: #991b1b; padding: 2px 8px; border-radius: 4px; font-size: 13px; }
.risk-criminal,.tag-purple { background: #f3e8ff; color: #6b21a8; padding: 2px 8px; border-radius: 4px; font-size: 13px; }

/* Statute-quote block (Hard Rule 10 — verbatim 法条 引用) */
.statute-quote {
  background: #f0f9ff;
  border-left: 4px solid #1a365d;
  padding: 14px 18px;
  margin: 12px 0;
  font-family: 'Songti SC', 'SimSun', '宋体', serif;
  font-size: 15px;
  color: #0c4a6e;
}

/* Lawyer-recommendation banner (Hard Rule 3) */
.lawyer-banner {
  background: #fee2e2;
  border: 2px solid #dc2626;
  color: #991b1b;
  padding: 14px 18px;
  margin: 16px 0;
  border-radius: 8px;
  font-weight: 600;
  font-size: 15px;
}

/* Time-limit countdown box (Hard Rule 8) */
.time-limit-box {
  background: #fffbeb;
  border-left: 4px solid #f59e0b;
  padding: 12px 16px;
  margin: 12px 0;
  font-size: 14px;
}
.time-limit-box .countdown-urgent { color: #dc2626; font-weight: 700; }

/* Devil's Advocate box (Hard Rule 6) */
.devil-box {
  background: #fff7ed;
  border-left: 4px solid #ea580c;
  padding: 14px 18px;
  margin: 14px 0;
}
.devil-box::before { content: "⚠️ Devil's Advocate"; display: block; font-weight: 700; color: #9a3412; margin-bottom: 8px; }

/* Source-reliability stars (Hard Rule 11) */
.reliability-5 { color: #fbbf24; font-size: 14px; } /* ★★★★★ */

/* Region-difference notice */
.region-notice {
  background: #f0fdfa;
  border-left: 4px solid #0d9488;
  padding: 12px 16px;
  margin: 12px 0;
  font-size: 14px;
}

/* PII-desensitized label */
.pii-mask {
  background: #f1f5f9;
  color: #475569;
  padding: 1px 6px;
  border-radius: 3px;
  font-family: monospace;
  font-size: 13px;
}

/* Font stack */
font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'PingFang SC', 'Microsoft YaHei', sans-serif;

/* Font sizes */
H1: 28px; H2: 22px; H3: 17px; body: 15px; table: 14px;

/* Page width — readable on mobile + desktop */
max-width: 980px; margin: 0 auto; padding: 0 16px;

/* Viewport meta tag — mandatory */
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

## Top-of-Report Notice Bar

Always render at the top (when applicable):

```html
<!-- High-risk red banner (Hard Rule 3) — mandatory when criminal / cross-border / >¥1M / 人身 / 复杂股权 -->
<div class="lawyer-banner">
  ⚠️ 本案 涉及 [criminal / cross-border / >¥1M / 人身 / 复杂股权] — 强烈建议 委托 执业律师 出具 正式 法律意见 + 代理. 本报告 是 决策支持, 不构成 正式法律意见.
</div>

<!-- Time-limit countdown banner (Hard Rule 8) -->
<div class="time-limit-box">
  ⏰ <strong>关键 时效 倒计时</strong>: 工伤认定 申请 仅剩 <span class="countdown-urgent">N 天</span> (截止 YYYY-MM-DD); 错过 → 工伤待遇 全部 丧失.
</div>

<!-- Region notice -->
<div class="region-notice">
  📍 本报告 适用 <strong>江苏 / 苏州 (<your-region>)</strong> 司法 实务. 跨地域 差异 见 第 N 节 "跨地域 提示".
</div>
```

## PII Desensitization Helper

Per Hard Rule 7, the report MUST automatically replace personal identifiers. Use these mappings consistently throughout the report:

| 原始 PII | 报告 中 替换 为 |
|---|---|
| 自然人 姓名 | `[当事人A]` / `[当事人B]` / `[员工C]` / `[配偶D]` / `[父亲]` / `[母亲]` (角色化) |
| 公司 全称 / 简称 | `[公司A]` / `[公司B]` / `[集团]` / `[关联方C]` |
| 案号 | `[案件C]` / `[(YYYY)苏xxx民终xxxx — 已脱敏]` |
| 身份证号 / 护照号 | `[身份证号 已脱敏]` / `[护照号 已脱敏]` |
| 银行账户 | `[银行账号 已脱敏 — 末四位 XXXX]` |
| 手机 / 邮箱 | `[手机 已脱敏 — 末四位 XXXX]` / `[邮箱 已脱敏 — *@example.com]` |
| 详细 地址 | `[地址 已脱敏 — XX 区 XX 街道]` |
| 房产 产权证号 | `[产权证号 已脱敏]` |
| 工资 / 营业额 / 资产 等 敏感金额 (在概念层面) | 保留 数额 (这是 法律分析 必要 信息) |

**Implementation hint** (HTML output time):
```html
<span class="pii-mask">[当事人A]</span>
```

**Raw input preservation**: 真实 PII 必须 单独 存 `evidence/raw-input.md` (operator-only, 不入 报告). 报告 引用 时 用 角色化 / 脱敏 形式.

## Template 1 — Q&A 答疑 (单 / 多 问题答疑)

```
[Header band 含 报告 标题 + 副标题 + 报告 时间 + 适用 场景 (Scenario 1 / 2)]

[Top notice bar — 视情况 render]

[Section: 任务 重述]
- 操作员 提问 (脱敏 后)
- 场景 检测 结果 + 适用 profile

[Section: 速答 (TL;DR)]
2-3 句 直接 回答 + 1-2 句 关键 caveat

[Section: 详细 分析 — Section per question]
### Q1: [问题]

**结论**: [加 risk-color tag]

**法律 依据** (5-source 覆盖, Hard Rule 5):
- 法条原文 (statute-quote 块, verbatim) — ★★★★★
- 司法解释 (statute-quote 块, verbatim) — ★★★★★
- 指导性案例 / 公报案例 — ★★★★ — 案号 + 法院 + 裁判 摘要
- 学术 评论 — ★★ — 作者 + 文献名 + 链接 OR 引用页
- 实务 指引 — ★ to ★★★ — 律所 / 法务 文章 + 链接

**适用条件**: ...

**风险点**: ...

**操作 建议**: 1 / 2 / 3 ...

**路径 推荐**: [5-dimension path table — Hard Rule 9 — only for dispute briefs]

**时效 倒计时** [Hard Rule 8]: ...

**Devil's Advocate** [Hard Rule 6]: ≥3 反向 论证

[Section: 跨地域 提示 — Hard Rule 4]
[Section: 后续 行动 清单]
[Section: 证据 清单 + 来源 — links to evidence/INDEX.md]
[Section: Footer — 出具时间 + 适用范围 + 免责声明]
```

## Template 2 — 合同条款 审查 (Contract Clause Review)

```
[Header band: 合同 名称 + 双方 (脱敏) + 审查 日期 + 报告版本]

[Top notice bar — 视情况]

[Section: 合同 元信息]
- 合同 名称 / 类型 / 双方 (脱敏) / 标的 / 总金额 / 期限 / 适用法律 / 争议解决

[Section: 总体 评价 — Risk Heat-Map]
| Article 范围 | 红色 数 | 橙色 数 | 绿色 数 | 综合 风险等级 |
|---|---|---|---|---|

[Section: 逐条 审查 (per the 20-point checklist + actual contract structure)]

### Article N — [topic]
**评级**: [🔴/🟡/🟢 tag]
**原文** (statute-quote 块): "..."
**问题**: ...
**法条 / 司法解释 依据**: ...
**修改 建议** (redline format):
  - 删除: ~~"..."~~
  - 替换 为: "..."
  - 新增: "..."
**谈判 backup**: 若 对方 不接受, 退而求其次 的 表述
**风险 备注**: ...

[Section: 修改后 全文 — full redlined version 或 单独 整理 修改建议 表格]

[Section: 关键 谈判 要点]
1. P0 — 必须 修改 (否则 不签)
2. P1 — 强烈 建议 修改 (可让步 但 留 reservation)
3. P2 — 建议 修改 (锦上添花)

[Section: Devil's Advocate — 若 完全 按本 修改建议 + 对方 接受 → 仍 可能 出现 哪些 风险]

[Section: 跨地域 提示 / 时效 倒计时 (若 涉及)]

[Section: 证据 清单 + Footer]
```

## Template 3 — 法律 文书 草稿 (Document Drafting — 申请书 / 律师函 / 通知 / 协议 / 答辩 / 异议)

```
[Header band: 文书 类型 + 用途 + 当事人 (脱敏) + 起草 日期]

[Top notice bar — 视情况]

[Section: 文书 用途 + 法律 依据]
- 用途: 申请 仲裁 / 主张 权利 / 协议 解除 / 等
- 法律 依据: ...
- 时效 / 程序 注意: ...

[Section: 推荐 文书 草稿 — full text]
<pre class="document-draft" style="background: #f8fafc; padding: 16px; border-radius: 6px; white-space: pre-wrap; font-family: 'Songti SC', serif;">
[完整 文书 文本, 含 抬头 / 当事人 / 主体 内容 / 落款 / 附件 list]
</pre>

[Section: 关键 段落 解释]
- [Paragraph N] — 为什么 这么 写; 法律依据
- ...

[Section: 替代 表述 (若 操作员 不 接受 部分语句)]
| 原 表述 | 替代 1 (温和) | 替代 2 (强硬) | 各自 法律效果 |

[Section: 操作 流程 + 时效 倒计时]
1. 起草 (本报告 已完成)
2. 律师 / 操作员 复核 (推荐)
3. 签字 / 盖章
4. 送达 (方式 / 留证)
5. 后续: 对方 答复 / 不答复 → 下一步

[Section: Devil's Advocate — 若 用 此 文书, 对方 可能 用什么 反向 论证]

[Section: 证据 / 附件 清单 + Footer]
```

## Template 4 — 法律 风险 评估 报告 (Risk Assessment)

```
[Header band: 评估 主题 + 评估 范围 + 评估 日期 + 评估 版本]

[Top notice bar]

[Section: 任务 重述 + 边界]

[Section: 4-Dimension Risk Matrix — Hard Rule + frameworks reference]

| 维度 | 概率 | 影响 | 综合评分 (0-10) | 颜色 | 缓解 优先级 |
|---|---|---|---|---|---|
| 合规 | 高 | 中 | 7 | 🔴 | P0 |
| 民事 | 中 | 高 | 7 | 🔴 | P0 |
| 行政 | 低 | 中 | 4 | 🟡 | P1 |
| 刑事 | 低 | 极高 | 5 | 🟣 | P0 |

[Section: 每维度 详细 分析 — Section per dimension]

### 维度 N: [Compliance / Civil / Admin / Criminal]

**当前 状态**: [描述]
**触发 法条**: [list]
**潜在 后果** (轻 → 重):
  1. [轻] ...
  2. [中] ...
  3. [重] ...

**概率 评估** [based on 类似 案例 / 行业 实务]
**影响 评估** [金额 / 时间 / 业务影响 / 个人 影响]
**5-source 覆盖** [list]

[Section: 缓解 建议 — Prioritized + Time-bound]
| 缓解 措施 | 优先级 | 预计 投入 | 预计 效果 | 责任人 | 期限 |
|---|---|---|---|---|---|

[Section: Worst-Case Scenario + Devil's Advocate]
- 最 悲观 情形: ...
- 触发 条件: ...
- 应对: ...

[Section: 跨地域 + 时效 + 证据 + Footer]
```

## Template 5 — 案例 综述 (Case Synthesis)

```
[Header band: 综述 主题 + 时间范围 (e.g. 2022-2025) + 法院 范围 + 综述 日期]

[Top notice bar]

[Section: 检索 方法]
- 关键词组合 + 数据库 (Wenshu / 北大法宝 / 等) + 筛选 标准 + 案件数 (检索 N 件 / 筛选后 M 件)

[Section: 同案 对比 表 — at least 5-10 cases]
| 案号 | 法院 | 年份 | 案件 类型 | 关键事实 | 法律 关键问题 | 法院 裁判 思路 | 判决结果 | 与本案 异同 |

[Section: 法院 倾向 trend-line]
- 原告 / 被告 胜诉率 (近 3 年, 同类型 案件 ≥10 件)
- 调解率
- 适用 法条 / 司法解释 频次
- 法院 整体 倾向 (严 / 宽 / 中)

[Section: 主流 裁判 思路 — 细分]
1. 主流 思路 A (覆盖 X% 案件): 论证 + 代表 案例
2. 主流 思路 B (覆盖 Y% 案件): 论证 + 代表 案例

[Section: 反向 案例 — Devil's Advocate]
- 反向 案例 1: 案号 + 法院 + 关键 事实 + 与 主流思路 区别要素 + 启示
- 反向 案例 2: 同上

[Section: 对 操作员 本案 的 启示]
- 本案 与 主流思路 案例 的 共同点 + 区别要素
- 关键 抗辩 / 反 抗辩
- 实战 建议

[Section: 跨地域 + 时效 + 证据 + Footer]
```

## Template 6 — 立法 / 政策 brief (Legislation / Policy Brief)

```
[Header band: 立法 / 政策 名称 + 文号 + 颁布日期 + 施行日期 + brief 日期]

[Top notice bar]

[Section: 立法 / 政策 速览]
| 项目 | 内容 |
|---|---|
| 全称 | ... |
| 文号 | 法释 [YYYY] N 号 / 国发 [YYYY] N 号 / etc. |
| 颁布机关 | NPC / NPC 常委会 / 国务院 / 部委 / 最高院 / 等 |
| 颁布日期 | YYYY-MM-DD |
| 施行日期 | YYYY-MM-DD |
| 上位法 | 民法典 / 公司法 / 等 |
| 替代 / 修订 关系 | 替代 [旧法 / 旧解释] |

[Section: 条文 摘要 + 重点 解读]
### 第 N 条
**原文** (statute-quote — verbatim): "..."
**解读**: 与 旧法 的 区别 + 立法 目的 + 实务 影响
**触发 范围**: 哪些 行为 / 主体 / 场景 触发
**与 其他 法律 / 解释 的 衔接**: ...

[Section: 影响 分析 — 对 操作员 集团 / 个人]
- 直接 影响: ...
- 间接 影响: ...
- 时间表: 立即 / 过渡期 / 长期 影响 节点

[Section: 应对 建议 — 时间表]
| 时间节点 | 应对 行动 | 责任人 | 关键 风险 |
|---|---|---|---|
| 立即 (0-30 日) | ... | ... | ... |
| 短期 (1-3 月) | ... | ... | ... |
| 中期 (3-12 月) | ... | ... | ... |
| 长期 (>1 年) | ... | ... | ... |

[Section: Devil's Advocate — 立法 / 政策 仍可能 调整 的 信号]

[Section: 5-source 覆盖 + Footer]
```

## Output Composition Rules

- 复合 brief (e.g. "审一下这个合同 + 起草 律师函") → 在一份 报告里 组合 多个 Template (例: Template 2 + Template 3 各自 完整 section, 共享 header + footer)
- 跨 scenario (e.g. 涉及 公司 + 个人 双方) → 分别 标 scenario, 各 用 对应 profile (`personal-company-profile`)
- HTML 文件 必须 自包含 — 所有 CSS inline, 无 外部 字体 / 图片 (内嵌 base64 OK 但 仅 必要时)
- HTML 文件 必须 加 `<meta charset="UTF-8">` + `<meta name="viewport" content="width=device-width, initial-scale=1.0">`
- 文件 名: `report.html` (per PROTOCOL S3)

## Footer Template

每份 报告 必须 含:
```html
<footer style="margin-top: 40px; padding: 20px; background: #f8fafc; border-radius: 8px; font-size: 13px; color: #475569;">
  <p><strong>报告 出具 时间</strong>: YYYY-MM-DD HH:MM (UTC+8)</p>
  <p><strong>适用 范围</strong>: 本报告 仅 适用 于 上述 委托人 / 上述 事项; 未经 授权 不得 用于 其他 目的.</p>
  <p><strong>免责 声明</strong>: 本报告 是 基于 已获 资料 + 现行 有效 法律 + 司法实务 的 决策支持, 不构成 正式 法律 意见. 正式 法律意见 须 由 持有 中华人民共和国 律师 执业证书 的 律师 出具.</p>
  <p><strong>版本 + 修订</strong>: V1.0 (YYYY-MM-DD); 后续 修订 见 evidence/CHANGELOG.md.</p>
  <p><strong>证据 索引</strong>: 详见 evidence/INDEX.md.</p>
</footer>
```
