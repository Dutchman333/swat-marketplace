# Changelog

## 1.0.0 (2026-05-14)

- **feat:** initial release of the chinese-legal-advisor squad package
- **feat:** add seven domain skills:
  - `chinese-labor-law-reference` — labor / employment / social insurance / 工伤 reference library
  - `chinese-civil-code-reference` — Civil Code 7 books (general / property / contract / personality / marriage-family / inheritance / tort) + key SPC interpretations
  - `chinese-corporate-law-reference` — Company Law 2024 + PIPL + DSL + anti-unfair-competition + trade secret
  - `chinese-legal-frameworks` — 4-dimension risk matrix / 20-point contract checklist / 6+ document templates / case research methodology / dispute-path decision tree / time-limit reminder framework / regional-difference framework
  - `chinese-legal-deliverables` — six self-contained HTML report templates (Q&A / contract review / document drafting / risk assessment / case synthesis / legislation brief) with shared visual conventions and PII desensitization helper
  - `chinese-legal-platforms-directory` — registry of authoritative PRC legal information sources and search platforms (flk.npc.gov.cn, wenshu.court.gov.cn, 北大法宝, 威科先行, 12348, 法院公报, academic indexes)
  - `personal-company-profile` — embedded operator company group + family + asset profile with scenario detection rules
- **feat:** define 12 non-negotiable Hard Rules covering statute citation precision, version stamping, high-risk lawyer-recommendation banner, regional-difference disclosure, 5-source coverage, Devil's Advocate, PII desensitization, time-limit countdown, dispute-path comparison, Chinese verbatim statute quoting, source reliability rating ★1-5, and evidence preservation
- **feat:** auto-scenario detection (Company vs Personal) with mixed-signal default to Company
- **feat:** auto-deliverable detection by task keyword (Q&A / contract review / document drafting / risk assessment / case synthesis / legislation brief)
