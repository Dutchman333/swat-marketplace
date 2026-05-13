# Dutchman333's SWAT Marketplace

A personal capability catalog for the [SWAT](https://github.com/LangSensei/swat) system — published independently by [@Dutchman333](https://github.com/Dutchman333).

This repository follows the same structure as the [official SWAT marketplace](https://github.com/LangSensei/swat-marketplace) so any SWAT-compatible agent (or any AI that can fetch raw GitHub files) can install the squads and skills below.

---

## 📂 Contents

### Squads

| Name | Version | Description |
|---|---|---|
| [`purchase-advisor`](squads/purchase-advisor) | 1.0.0 | Cross-category procurement research — supplier investigation, brand/model comparison, multi-source price intelligence, RFQ analysis, and negotiation strategy. Outputs a self-contained Chinese HTML report. |

### Skills

| Name | Version | Description |
|---|---|---|
| [`price-channel-directory`](skills/price-channel-directory) | 1.0.0 | Standardized list of Chinese price-discovery channels (JD/Tmall/1688/Pinduoduo/Taobao/etc.) with category routing rules. |
| [`procurement-deliverables`](skills/procurement-deliverables) | 1.0.0 | Self-contained HTML output templates for procurement reports (4 deliverable shapes + color-coded tag conventions). |
| [`procurement-frameworks`](skills/procurement-frameworks) | 1.0.0 | Methodology library for procurement decisions: 5R Model, Kraljic Matrix, Carter 10Cs, TCO, ABC/XYZ, negotiation leverage. |
| [`solution-discovery`](skills/solution-discovery) | 1.0.0 | Open-vision research methodology — leverages 5-source coverage and anti-mainstream-bias guardrails when scouting brands/models. |
| [`supplier-due-diligence`](skills/supplier-due-diligence) | 1.0.0 | Standardized supplier background investigation checklist (~30 items across 5 categories: registration, financials, qualifications, reputation, risk signals). |

> **Squad → Skill dependency**: `purchase-advisor` depends on all 5 skills above plus 2 already-published upstream skills (`scientific-method`, `debrief`). Install those from the official marketplace if you don't have them.

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
