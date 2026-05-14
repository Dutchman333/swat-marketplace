---
name: chinese-legal-platforms-directory
version: "1.0.0"
description: PRC legal information sources and search platforms registry — official statute database, court judgment database, commercial legal databases, government legal aid, court bulletins, academic resources, practice publications — with platform comparison, search methodology, and 5-source cross-check protocol
---

# Chinese Legal Platforms Directory

A maintained registry of authoritative PRC legal information sources, with strengths, gotchas, and a routing decision tree for which platform to query in any given task.

## Use When

- Selecting which platform(s) to query for statutes, judicial interpretations, or case law
- Cross-checking a citation across multiple sources
- Verifying the current effective version of a statute (Hard Rule 2)
- Building the 5-source coverage required for any material claim (Hard Rule 5)
- Routing a Wenshu / 北大法宝 / 威科 / etc. retrieval subtask

## Statute / Regulation Platforms (法律 / 行政法规 / 部门规章)

| Platform | URL | Strength | Gotcha | Reliability |
|---|---|---|---|---|
| **国家法律法规数据库 (NPC)** | flk.npc.gov.cn | **Authoritative** for 法律 (NPC + NPC 常委会) + 行政法规 (国务院) + 监察法规 + 司法解释 (部分) + 地方性法规; 所有 历史版本 + 现行有效 标识 + 修订 时序 都 完整 | UI 不够 现代化; 部分 部委 规章 不收录 | ★★★★★ |
| **中国政府网 法律法规库** | www.gov.cn/zhengce/ | 国务院 行政法规 + 决定 + 通知 + 政府工作报告 全文 | 主要 国务院 文件; 司法解释 / 法律 仍 用 NPC | ★★★★★ |
| **司法部 中国法律法规检索系统** | search.chinalaw.gov.cn | 法律 + 行政法规 + 部门规章 + 司法解释 + 地方性法规 综合 | 部分 数据 滞后 NPC | ★★★★ |
| **中央政府门户网 法律法规** | 同 中国政府网 | (主要 政策 性文件) | (同上) | ★★★★ |

> **首选**: 引用 法律 / 行政法规 / 司法解释 → flk.npc.gov.cn 优先, 验证 现行 有效 + 最新 版本.

## Court Judgments / Cases (案例)

| Platform | URL | Strength | Gotcha | Reliability |
|---|---|---|---|---|
| **中国裁判文书网 (Wenshu)** | wenshu.court.gov.cn | 全国 各级 法院 生效判决 + 裁定 + 调解 全文; 公开 + 免费; 高级 检索 (法院 / 案由 / 时间 / 全文 等) | (a) 部分 案件 (涉密 / 涉个人隐私 / 国家利益) 不公开; (b) 近年 公开 数量 有所收紧; (c) 部分 高 影响 案件 撤回 | ★★★★ (普通生效判决); ★★★★★ (公报 / 指导性) |
| **最高人民法院 公报 + 指导性案例** | court.gov.cn (司法案例 / 案例指导栏目) | 最高院 官方 选定 — 具有 指导效力 (类案 应当 参照, 民诉法 / 民事诉讼解释) | 数量 有限 (累计 数百 件) | ★★★★★ |
| **江苏省高级人民法院 公报 + 典型案例** | jsfy.gov.cn (江苏 公报栏目) | 省 高院 选定; 江苏 + 苏州 / 无锡 / 常州 等 中院 / 基层法院 实务 倾向 重要 参考 | 数量 有限 | ★★★★ |
| **裁判文书网 (Wenshu) 指导性案例 专栏** | 同 wenshu | 最高院 + 高院 公报 重点 整理 | (同 Wenshu) | ★★★★★ |

> **首选**: 案例 检索 → Wenshu (普通) + 最高院 公报 / 指导性 (重大 / 复杂) + 江苏 高院 (本地 倾向).

## Commercial Legal Databases (付费, 综合)

| Platform | URL | Strength | Gotcha | Reliability |
|---|---|---|---|---|
| **北大法宝 (PKULAW)** | pkulaw.com | 法律 + 司法解释 + 案例 + 学术 + 实务 综合 + 强大 关联 检索; 中外 法律 综合; 历史 版本 完整 | 付费 (个人 / 律所 / 企业 订阅); 部分 内容 限 高级会员 | ★★★★★ |
| **威科先行 法律信息库 (WK / Wkinfo)** | wkinfo.com.cn | 综合 (法律 + 案例 + 实务 + 中外 法律); 比 北大法宝 在 涉外 / 国际 法律 略强 | 付费; UI 较新 | ★★★★★ |
| **法宝智能 (PKU 智能)** | (via 北大法宝) | AI 辅助 检索 + 类案 推荐 + 规则 提取 | 同 北大法宝 | ★★★★ |
| **无讼 案例 / 律师智库** | itslaw.com | 案例 + 律师 公开 文章; 部分免费 + 高级 付费 | 案例 来源 主要 仍 是 Wenshu | ★★★ |
| **聚法案例** | jufaanli.com | 案例 数据库 + 法律 智能 检索 | 主要 Wenshu 数据; 收费模式 | ★★★ |
| **alpha 法律研究** | alphalawyer.cn | 律师 智能 + 案例 + 类案 + 检索 + 行业 报告; 律所 popular | 付费; 个人 用户 限 | ★★★★ |

> **首选**: 操作员 集团 / 个人 长期 用 — 推荐 订阅 北大法宝 OR 威科先行 (任选一; 二选一 可覆盖 80% 需求). 律师所 联合 操作 时 — 律所 通常 已订阅.

## Public Legal Aid (公益)

| Platform | URL | Strength | Gotcha | Reliability |
|---|---|---|---|---|
| **12348 中国法律服务网** | www.12348.gov.cn | 司法部 + 各地 司法局 — 免费 法律咨询 + 律师 推荐 + 公证 / 仲裁 / 调解 / 法律援助 入口; 24/7 在线; 部分 免费 一对一 律师 答疑 | 免费 服务 — 不能替代 付费 律师 + 复杂案件 | ★★★ (适合 一般咨询) |
| **法律援助 中心 (司法局 各地)** | (各地 司法局 热线 + 柜面) | 符合 条件 (经济困难 / 老年人 / 残疾人 / 等) 可 申请 免费 律师 代理 | 申请 条件 严; 案件类型 限 | ★★★ |
| **公证处** | (各地 公证处) | 遗嘱 公证 / 财产协议 公证 / 委托书 公证 / 婚前协议 公证 / 等 | 公证 是 形式 / 真实性 加强, 不解决 实体 法律问题 | ★★★★★ (在其专属领域) |

## Academic Resources (学术 — 法学 期刊 / 教科书)

| Platform | URL | Strength | Gotcha | Reliability |
|---|---|---|---|---|
| **中国知网 (CNKI)** | www.cnki.net | 法学 期刊 (中国法学 / 法学研究 / 中外法学 / 政法论坛 / 法律科学 / 现代法学 / 比较法研究 等) + 硕博 论文 + 会议 论文 | 付费; 个人 用户 单篇 收费 | ★★★★ |
| **万方 数据** | wanfangdata.com.cn | 同 CNKI 类似 综合 | 付费 | ★★★ |
| **维普 中文期刊** | cqvip.com | 同上 | 付费 | ★★★ |
| **中国法律 评论** | 各刊 官网 | 高 引 法学 期刊 (人大复印资料 + 法学 顶刊) | 部分 限 付费 / 机构 订阅 | ★★★★ |
| **法学 教科书** (王利明 / 江平 / 梁慧星 / 杨立新 / 徐国栋 / 马怀德 等) | (出版 + 图书馆) | 体系化 + 学术 共识 + 立法 沿革 解读 | 部分 教科书 滞后 民法典 + 公司法 修订 | ★★★ to ★★★★ |

## Practice Channels (实务 — 公众号 + 律所 + 法务社区)

| Channel | Type | Strength | Gotcha | Reliability |
|---|---|---|---|---|
| **无讼 (公众号 / 平台)** | 公众号 + 网站 | 高质量 实务 + 案例 解读; 律师 / 法务 popular | 商业化 内容 多 | ★★★ |
| **庭立方** | 公众号 | 刑事 实务 — 顶级 影响力 | 主要 刑事 | ★★★★ |
| **法天使** | 公众号 + 网站 | 合同 模板 + 公司 治理 实务 — 综合 | 需 注册 / 部分付费 | ★★★ |
| **iCourt** | 公众号 + 培训 | 律师 思维 + 法律 检索 + 类案 实务 — 培训型 | 培训 销售 性质 | ★★★ |
| **保护伞 (Smartumbrella)** | 公众号 | 公司 法 + 投融资 实务 | 偏 商业 | ★★★ |
| **学法网 / 大律师网** | 网站 / 公众号 | 公益 + 律师介绍 + 普法 | 质量 不一 | ★★ |
| **律所 自媒体** (君合 / 中伦 / 金杜 / 海问 / 锦天城 / 大成 / 等 顶 30 律所 公众号) | 公众号 | 实务 评论 + 法律 修订 解读 + 行业 brief — 高 质量 | 各律所 角度 偏向 自身 业务; 应交叉 阅读 | ★★★★ |
| **苏州本地 律师 / 律所 公众号** (江苏世纪同仁 / 江苏苏港 / 江苏致邦 / 江苏勤业 / 江苏 国浩 苏州办公室 等) | 公众号 | 江苏 / 苏州 本地 实务 倾向 — 相关性 高 | 数量 多 + 质量 不一 | ★★ to ★★★★ |

> **首选**: 操作员 关注 —
> - 公司 治理 / 投融资 — 君合 / 中伦 / 海问 公众号
> - 劳动 / HR — 江三角 律所 / iCourt 劳动 系列
> - 婚姻 / 家事 / 继承 — 段和段 / 上海家与家 公众号
> - 数据 合规 / 个保 — 安杰世泽 / 中伦 / 君合 数据合规 团队
> - 江苏 / 苏州 实务 — 国浩 苏州 / 江苏 世纪同仁

## Specific Document / Process Lookup

| Need | Platform / Office |
|---|---|
| 工商登记 (公司 营业执照 / 股东 / 法定代表人 等) | 国家企业信用信息公示系统 (gsxt.gov.cn) — 免费 |
| 商事登记 + 股权 + 章程 (深度) | 启信宝 / 天眼查 / 企查查 (付费) |
| 不动产 登记 (房产 产权) | 苏州市 不动产登记中心 (操作员 持有 房产 — 应 自查 当前登记 状态) |
| 工伤认定 申请 / 劳动能力 鉴定 | <本区> 人社局 工伤科 / 苏州市 劳动能力 鉴定委员会 |
| 劳动 仲裁 申请 | <本区> 劳动 人事 争议 仲裁院 |
| 民事 / 行政 起诉 | <本区> 人民法院 (一审); 苏州市 中级人民法院 (二审) |
| 商事 仲裁 (合同 含 仲裁 条款) | 中国国际经济贸易仲裁委员会 (CIETAC) / 上海仲裁委员会 / 北京仲裁委员会 / 深圳国际仲裁院 / 苏州仲裁委员会 |
| 信访 / 行政 复议 | <本区> 人民政府 / 苏州市 人民政府 |
| 公证 (遗嘱 / 委托 / 财产协议 / 等) | 苏州市公证处 (<your-region>办事处 OR 主城区) |

## Search Methodology — 5-Source Cross-Check Protocol (Hard Rule 5)

**Per material conclusion, retrieve and cross-check across 5 source categories**:

```
Step 1: 法条 原文 (statute primary text)
   → flk.npc.gov.cn 输入 法律名称 → 选择 现行有效 + 最新版本
   → 复制 verbatim 法条 (Hard Rule 10) → 入 evidence/

Step 2: 司法解释 (judicial interpretation)
   → flk.npc.gov.cn / court.gov.cn / 北大法宝 → 输入 法律名称 + "司法解释" → 选择 与 主条 配套的 解释
   → 复制 verbatim → 入 evidence/

Step 3: 指导性 案例 / 公报 案例
   → court.gov.cn 司法案例 / 案例指导栏目 → 输入 法条 编号 + 关键词
   → OR 北大法宝 / 威科 类案 推荐
   → 至少 1-2 件 高 reliability 案例 → 入 evidence/

Step 4: 学术 评论 (≥1)
   → CNKI / 知网 → 输入 法条 + 关键词 → 筛选 "中国法学" / "法学研究" / "法律科学" / "中外法学" 等 顶刊 → 找 3-5 年内 最新 评论
   → 引用页 + 链接 → 入 evidence/

Step 5: 实务 指引 (≥1)
   → 律所 公众号 / 无讼 / iCourt / 法天使 / 庭立方 — 顶 30 律所 优先
   → 找 3 年内 最新 实务 评论 / 操作 指引
   → 链接 + 摘要 → 入 evidence/

最后: 合并 引用 + reliability ★ tag → 入 报告 references appendix
```

## Statute Version Verification Protocol (Hard Rule 2)

```
1. 进入 flk.npc.gov.cn → 输入 法律 全称
2. 查看 颁布 + 修订 时序 表
3. 选择 最新 版本 + 验证 "现行 有效" 标识
4. 复制 verbatim 法条 + 标 版本 + 标 effective date 范围
5. 若 案件 法律事实 发生 在 旧法 期间 → 适用 旧法 (查 历史 版本)
6. 若 案件 跨 新旧 法 → 适用 民法典 时间效力 司法解释 (法释 [2020] 15 号)
```

## Region-Aware Routing

For 操作员 (Suzhou <your-region>):

| Type | Primary route | Backup |
|---|---|---|
| 法条 / 司法解释 | flk.npc.gov.cn | court.gov.cn / 北大法宝 |
| 江苏 + 苏州 实务 案例 | jsfy.gov.cn (江苏 高院) + Wenshu 筛选 江苏 + 苏州 中院 | 国浩 苏州 / 江苏世纪同仁 公众号 |
| 跨地域 比较 (深圳 / 北京 / 上海 / 广州) | Wenshu 各地区 + 各 高院 公报 | 律所 跨地域 实务 评论 |
| 工商 / 不动产 / 工伤 / 仲裁 程序 | 各 行政 / 准司法 机关 直接 申请 | 12348 + 公证处 + 律师 |

## Evidence Preservation Convention (Hard Rule 12)

每次 retrieve, 必须 存:
```
evidence/
├── INDEX.md
│     | 文件名 | 来源 | URL | 检索时间 (UTC) | 适用 法条 / 案号 | 报告 引用 章节 | reliability ★ |
├── statute-001-民法典-第1062条.pdf  (OR .png screenshot OR .md verbatim)
├── interpretation-001-婚姻家庭编-司法解释一.pdf
├── case-001-(2024)苏05民终xxxx.pdf
├── case-002-(2023)最高法民终xxxx.pdf
├── academic-001-王利明-民法典共同财产-中国法学-2022-03.pdf
├── practice-001-海问-2024离婚共同财产实务.pdf
└── ...
```

INDEX.md 一定 维护 — 报告 输出 时 链接 evidence/INDEX.md.
