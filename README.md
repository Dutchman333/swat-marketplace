# Dutchman333's SWAT Marketplace

A personal capability catalog for the [SWAT](https://github.com/LangSensei/swat) system — published independently by [@Dutchman333](https://github.com/Dutchman333).

This repository follows the same structure as the [official SWAT marketplace](https://github.com/LangSensei/swat-marketplace) so any SWAT-compatible agent (or any AI that can fetch raw GitHub files) can install the squads and skills below.

---

## 📂 Contents

### Squads

| Name | Version | Description |
|---|---|---|
| [`purchase-advisor`](squads/purchase-advisor) | 1.0.0 | Cross-category procurement research — supplier investigation, brand/model comparison, multi-source price intelligence, RFQ analysis, and negotiation strategy. Outputs a self-contained Chinese HTML report. |
| [`travel-planner`](squads/travel-planner) | 1.0.0 | Personalized travel planning advisor — destination scouting, itinerary design, hotel/flight comparison with multi-platform price intelligence, and customized recommendations driven by an embedded family profile. Outputs a self-contained Chinese HTML report. |
| [`chinese-legal-advisor`](squads/chinese-legal-advisor) | 1.0.0 | PRC legal advisor — labor law, civil code, corporate law, personal information protection, data security. Dual scenario (Company HR/contracts/disputes + Personal matters: marriage/inheritance/property). Outputs Q&A / contract review / legal document drafts / risk assessments / case syntheses / legislation briefs in Chinese HTML. |

### Skills

| Name | Version | Description |
|---|---|---|
| [`price-channel-directory`](skills/price-channel-directory) | 1.0.0 | Standardized list of Chinese price-discovery channels (JD/Tmall/1688/Pinduoduo/Taobao/etc.) with category routing rules. |
| [`procurement-deliverables`](skills/procurement-deliverables) | 1.0.0 | Self-contained HTML output templates for procurement reports (4 deliverable shapes + color-coded tag conventions). |
| [`procurement-frameworks`](skills/procurement-frameworks) | 1.0.0 | Methodology library for procurement decisions: 5R Model, Kraljic Matrix, Carter 10Cs, TCO, ABC/XYZ, negotiation leverage. |
| [`solution-discovery`](skills/solution-discovery) | 1.0.0 | Open-vision research methodology — leverages 5-source coverage and anti-mainstream-bias guardrails when scouting brands/models. |
| [`supplier-due-diligence`](skills/supplier-due-diligence) | 1.0.0 | Standardized supplier background investigation checklist (~30 items across 5 categories: registration, financials, qualifications, reputation, risk signals). |
| [`personal-travel-profile`](skills/personal-travel-profile) | 1.0.0 | **Template** for the operator's embedded travel profile — family composition, scenarios, loyalty memberships, airline / hotel preferences, budget bands, off-peak preference, visa status, avoid list. **Customize before first use** — see the file's Setup section. |
| [`travel-frameworks`](skills/travel-frameworks) | 1.0.0 | Travel planning methodology library — pacing rules (Scenario 1 family / Scenario 2 couple-or-solo), budgeting templates, destination intelligence checklist, and off-peak detection rules. |
| [`travel-platforms-directory`](skills/travel-platforms-directory) | 1.0.0 | Travel booking and price-comparison platform registry — domestic vs international OTAs, airline aggregators, hotel direct-booking sites (IHG / Marriott / Hilton / etc.), and a category-to-platform decision tree. |
| [`travel-deliverables`](skills/travel-deliverables) | 1.0.0 | Self-contained HTML output templates for the six standard travel deliverables — destination comparison, hotel comparison, flight comparison, day-by-day itinerary, budget breakdown, and visa advisory. |
| [`chinese-labor-law-reference`](skills/chinese-labor-law-reference) | 1.0.0 | PRC labor law reference library — 劳动法 / 劳动合同法 / 社会保险法 / 工伤保险条例 / 三期女职工保护 / 工时制度 / 工会法 / 工资支付 / 劳动争议调解仲裁 with cross-region tendency notes. 8 deep reference files. |
| [`chinese-civil-code-reference`](skills/chinese-civil-code-reference) | 1.0.0 | PRC Civil Code 7-book reference — 总则 / 物权 / 合同 / 人格权 / 婚姻家庭 / 继承 / 侵权责任 with key SPC interpretations index. 8 deep reference files. |
| [`chinese-corporate-law-reference`](skills/chinese-corporate-law-reference) | 1.0.0 | PRC corporate, data, and competition law reference — 公司法 (2024 修订) / 个人信息保护法 / 数据安全法 / 反不正当竞争法 / 商业秘密. 4 deep reference files. |
| [`chinese-legal-frameworks`](skills/chinese-legal-frameworks) | 1.0.0 | PRC legal analysis methodology — risk assessment matrix (合规 / 民事 / 行政 / 刑事), contract review checklist, document drafting templates, case research methodology, dispute-path decision tree (谈判 / 调解 / 仲裁 / 诉讼 / 报警), prescription-period reminder framework. |
| [`chinese-legal-deliverables`](skills/chinese-legal-deliverables) | 1.0.0 | Self-contained Chinese HTML output templates for 6 legal deliverables — Q&A advisory, contract review, legal document draft, risk assessment, case synthesis, legislation brief. PII-desensitization helper baked in. |
| [`chinese-legal-platforms-directory`](skills/chinese-legal-platforms-directory) | 1.0.0 | PRC legal information sources directory — 国家法律法规数据库 / 中国裁判文书网 / 北大法宝 / 威科先行 / 各级法院公报 / 12348 / 实务公众号. 5-source cross-check methodology. |
| [`personal-company-profile`](skills/personal-company-profile) | 1.0.0 | **Template** for the operator's company-and-personal legal profile — group structure, employee mix, labor history, certifications, family composition, asset profile, succession-track context, scenario detection. **Customize before first use** — see the file's Setup section. |

> **Squad → Skill dependencies**:
> - `purchase-advisor` depends on the 5 `procurement-*` / `price-channel-directory` / `solution-discovery` / `supplier-due-diligence` skills above + 2 upstream skills (`scientific-method`, `debrief`).
> - `travel-planner` depends on 4 `travel-*` / `personal-travel-profile` skills above + 1 upstream skill (`scientific-method`).
> - `chinese-legal-advisor` depends on 6 `chinese-*` / `personal-company-profile` skills above + 2 upstream skills (`scientific-method`, `debrief`).
>
> Install upstream skills from [LangSensei/swat-marketplace](https://github.com/LangSensei/swat-marketplace) if you don't have them.

---

## 🚀 Installation

### Option A — manual install into `~/.swat/`

```bash
# clone this repo somewhere
git clone https://github.com/Dutchman333/swat-marketplace ~/swat-marketplace-dutchman333

# symlink (or copy) the squad and skills into your local SWAT dirs
ln -s ~/swat-marketplace-dutchman333/squads/purchase-advisor   ~/.swat/squads/purchase-advisor
for skill in price-channel-directory procurement-deliverables procurement-frameworks solution-discovery supplier-due-diligence; do
  ln -s ~/swat-marketplace-dutchman333/skills/$skill ~/.swat/skills/$skill
done
```

On Windows (PowerShell, run as admin for symlinks or just use `Copy-Item -Recurse`):

```powershell
git clone https://github.com/Dutchman333/swat-marketplace $HOME\swat-marketplace-dutchman333
Copy-Item "$HOME\swat-marketplace-dutchman333\squads\purchase-advisor" "$HOME\.swat\squads\purchase-advisor" -Recurse
foreach ($s in 'price-channel-directory','procurement-deliverables','procurement-frameworks','solution-discovery','supplier-due-diligence') {
  Copy-Item "$HOME\swat-marketplace-dutchman333\skills\$s" "$HOME\.swat\skills\$s" -Recurse
}
```

### Option B — fetch raw files directly (any AI / LLM agent)

Each squad and skill is a couple of plain Markdown files. Any agent that can `curl` or `fetch` from raw.githubusercontent.com can read them:

```
https://raw.githubusercontent.com/Dutchman333/swat-marketplace/main/squads/purchase-advisor/MANIFEST.md
https://raw.githubusercontent.com/Dutchman333/swat-marketplace/main/skills/<skill-name>/SKILL.md
```

The `MANIFEST.md` / `SKILL.md` files contain YAML frontmatter (`name`, `version`, `description`, `dependencies`) followed by the prose definition — exactly what an LLM needs to load the capability into its context.

---

## 🔗 Relationship with the official marketplace

This is an **independent personal catalog**, not a fork. It complements [LangSensei/swat-marketplace](https://github.com/LangSensei/swat-marketplace):

- The official marketplace ships the core SWAT system, its meta-squads, and broad-coverage skills.
- This repo ships my own domain-specific work (procurement / sourcing) that hasn't been merged upstream.
- Where there is a name collision, the **official marketplace** wins — install from there first, then layer this on top only for the names that are unique here.

If a squad / skill from this repo gets accepted upstream later, it will be removed from here to avoid duplication.

---

## 📝 License

[MIT](LICENSE) — feel free to fork, adapt, and republish, with attribution.

## 🙏 Credits

- [SWAT](https://github.com/LangSensei/swat) by [@LangSensei](https://github.com/LangSensei) — the underlying agent runtime and protocol that makes this catalog meaningful.
- Squad/skill content here is original work by [@Dutchman333](https://github.com/Dutchman333), informed by classical procurement frameworks (5R, Kraljic, Carter 10Cs).
