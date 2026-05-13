---
name: personal-travel-profile
version: "1.0.0"
description: Embedded travel profile of the squad operator — family composition, scenarios, loyalty memberships, airline / hotel preferences, budget bands, off-peak preference, visa status, and avoid list. Customize this file with your own values before first use.
---

# Personal Travel Profile  &nbsp;<sub>· Template version</sub>

> **🔧 SETUP REQUIRED.** This skill is the **personal config** of the `travel-planner` squad. Before your first run, **edit every section below** marked with `<TODO: ...>` to fit your situation. The squad will read this file at the start of every operation and apply your preferences automatically.
>
> **Privacy note:** This file lives in your local SWAT installation. Do not commit your filled-in version back to a public repo unless you've reviewed every line for PII you're comfortable sharing.

This skill encodes the operator's personal travel profile. The travel-planner squad must read this skill **first** in every operation and apply the profile unless the brief explicitly overrides specific items.

## How to Apply

1. Load this profile at the start of every operation.
2. Use the **Scenario Detection** rules below to pick Scenario 1 vs Scenario 2 based on the brief's wording.
3. Apply preferences automatically — never ask the operator to re-confirm what's already encoded here.
4. The brief can override any item; when it does, log the override in `findings.md`.

---

## Family Composition  &nbsp;<sub><TODO: 按你家庭情况调整></sub>

| Member | Role | Notes |
|---|---|---|
| Operator (you) | `<TODO: e.g., Father / Mother / Solo>` | Lead planner, decides budget |
| Spouse | `<TODO: present / not applicable>` | Equal decision partner; loyalty: `<TODO: e.g., Marriott Gold>` |
| Child | `<TODO: e.g., 3 years old>` | Travels with the family |
| Nanny / Helper | `<TODO: optional / not applicable>` | Counts as 1 adult for room / flight planning when present |

**Default headcount for Scenario 1**: `<TODO: e.g., 2 adults + 1 child, or 3 adults + 1 child if nanny>`.

**Language abilities**: `<TODO: e.g., both parents fluent in English / Mandarin only / etc.>`. This affects which destinations are language-barrier-free.

## Scenarios

### Scenario 1 — Family with toddler / young child (+ optional nanny)

- **Pace**: relaxed, one major activity per half-day, nap-window respected (default 13:30-15:30 — adjust to your child)
- **Hotel preference**: `<TODO: e.g., high-end (5-star or upper-upscale 4-star), spacious room or suite, kid amenities>`
- **Activity bias**: parks (Disney / Universal / Legoland / aquarium / zoo), nature (gentle hikes, beach, hot springs with kid pool), city sightseeing with stroller-friendly routes
- **Avoid**: `<TODO: e.g., night markets > 21:00, rowdy bars, long single-day drives (>2h), high-altitude trekking, water sports for adults>`

### Scenario 2 — Couple alone or solo

- **Pace**: medium-deep, willing to do 3-4 activities per day
- **Bias**: `<TODO: e.g., international destinations preferred; outdoor hiking, cultural depth, fine dining, scenic train / drive routes>`
- **Comfortable with**: `<TODO: e.g., long flights, multi-leg routing, language-barrier destinations>`
- **Avoid**: `<TODO: e.g., package tours, themed parks, generic shopping malls>`

### Scenario Detection Rules

| Brief contains | → Scenario |
|---|---|
| 带女儿 / 带孩子 / 一家人 / 全家 / 父母带 / with kid / with daughter | 1 |
| 我和老婆 / 夫妻 / 我和我老婆 / 我自己 / 独行 / couple / solo / just us | 2 |
| 出差 / 商务 | (out of scope — recommend rebooking through corporate channels) |
| Ambiguous | Default to **2** if international + outdoor keywords present; otherwise **1**; surface in Assumptions |

## Loyalty Memberships  &nbsp;<sub><TODO: 填入你的实际会员状态></sub>

| Program | Member | Tier | Key benefits to apply |
|---|---|---|---|
| **IHG One Rewards** | `<TODO: operator / spouse / —>` | `<TODO: e.g., Diamond / Diamond Elite / Spire / Ambassador / Platinum / Gold / Silver / —>` | If Ambassador or above: complimentary upgrade subject to availability, weekend benefit, free breakfast at IC, 4 PM late checkout, BOGO at IC, double points |
| **Marriott Bonvoy** | `<TODO: operator / spouse / —>` | `<TODO: e.g., Ambassador / Titanium / Platinum / Gold / Silver / —>` | Tier-dependent: Gold = 25% bonus points + 2 PM late checkout; Platinum+ adds breakfast + lounge + upgrade to suite |
| **Hilton Honors** | `<TODO: ...>` | `<TODO: ...>` | `<TODO: ...>` |
| **World of Hyatt** | `<TODO: ...>` | `<TODO: ...>` | `<TODO: ...>` |
| **Accor Live Limitless** | `<TODO: ...>` | `<TODO: ...>` | `<TODO: ...>` |
| **Shangri-La Circle** | `<TODO: ...>` | `<TODO: ...>` | `<TODO: ...>` |
| **Star Alliance / OneWorld / SkyTeam** | `<TODO: KrisFlyer / Asia Miles / etc.>` | `<TODO: e.g., Star Gold>` | Lounge access + extra baggage + priority |

**Application rule**: when comparing hotels of similar price and location, **always prefer** properties that activate one of these memberships. Show the dollar value of the benefits in the comparison.

## Airline Preferences

- **Preferred** (default search filter): 5-star international carriers — Singapore Airlines, Cathay Pacific, ANA, JAL, Qatar Airways, Emirates, Etihad, EVA Air, Lufthansa, Swiss, Turkish Airlines
- **Default avoid** (customize): `<TODO: e.g., mainland Chinese carriers (Air China, China Eastern, China Southern, Hainan, Xiamen, Spring, Juneyao). Recommend only when (a) only carrier on the route, or (b) >= 50% cheaper AND >= 3h faster.>`
- **Cabin class**: `<TODO: e.g., economy by default; premium economy / business if budget allows or operator specifies; long-haul (>= 10h) — surface premium economy upgrade option>`
- **Hub preference**: `<TODO: e.g., HKG, SIN, NRT/HND, ICN, DOH, DXB favored; PEK/PVG/CAN avoided unless necessary>`
- **Aircraft preference**: `<TODO: e.g., enjoy A380 / 787 / A350; avoid old 777-200 / older B767>`

## Budget Bands  &nbsp;<sub><TODO: 替换为你自己的预算></sub>

| Item | Default range | Stretch trigger |
|---|---|---|
| Hotel per night | `<TODO: ¥X – ¥Y>` | Region median > top of range → can go higher |
| Flight per person (international) | `<TODO: economy ¥X – ¥Y; PE: +50%; J: +200%>` | Long-haul / 5-star upgrade |
| Daily food (per adult) | `<TODO: ¥X – ¥Y>` | Michelin / fine dining day → up to ¥X |
| Daily activity / entry | `<TODO: ¥X – ¥Y>` | Special experiences (helicopter, private guide) |

When the destination's local cost level exceeds defaults (e.g., Tokyo, Zurich, NYC), surface the override and proceed; do not down-spec.

## Date / Timing Preferences

- **Off-peak preference**: `<TODO: strong / moderate / none>` — avoid Chinese statutory holidays, school summer (7 月中 - 8 月底) and winter (1 月下 - 2 月初) breaks
- **Schedule flexibility**: `<TODO: e.g., both parents have flexible schedules — when peak is detected, propose 2 alternative date windows>`
- **Trip length**: not fixed, depends on each request's context

## Visa Status  &nbsp;<sub><TODO: 按实际更新></sub>

| Visa | Status | Action |
|---|---|---|
| Japan multi-entry | `<TODO: held / not held>` | If held: no action; can travel anytime. If not: insert visa-prep notice. |
| Schengen | `<TODO: held / not held>` | If not held: insert "申根签证需提前 X 周办理"; recommend French / Spanish consulate routing |
| US (B1/B2) | `<TODO: held / not held>` | If not held: surface processing time (currently 2-12 months depending on consulate) |
| UK | `<TODO: held / not held>` | If not held: surface application requirement |
| Canada / Australia / NZ | `<TODO: held / not held>` | If not held: surface application requirement |
| Visa-free destinations (Thailand, Indonesia, UAE, Singapore, Malaysia, Korea (limited), etc.) | OK | Just confirm current visa-free policy hasn't lapsed |

Update this section whenever you obtain a new visa or one expires.

## Avoid List

**Never recommend**:

- Active war / civil-conflict zones (e.g., Ukraine, Syria, Yemen, parts of Sudan, Myanmar conflict areas, Israeli-Palestinian conflict zones during active escalation, etc.)
- Listed at 中国领事服务网 cs.mfa.gov.cn as 暂勿前往 / 谨慎前往 with operator's risk profile
- Extreme-poverty destinations with severely limited safe infrastructure for a young child (Scenario 1)
- Areas with active disease outbreaks (cholera, ebola, current notable epidemics)

`<TODO: append your own avoid items, e.g., specific cities you dislike, climates you can't tolerate>`

When in doubt, **flag and ask** rather than auto-recommend.

## Operator Self-Books

The operator handles all bookings personally. The squad's job is to deliver decision-ready comparisons with direct booking links — **not to book**.

## Override Convention

If a specific brief overrides any item above (e.g., "this trip skip Marriott", "this time we'll fly China Eastern because it's cheaper"), log it in the operation `findings.md`:

```
## Profile overrides this run
- Brief override: <override item>; reason: <why>
- Effective profile: <what we used>
```

This keeps the audit trail clean.

---

## 📝 First-Run Checklist

Before your first `travel-planner` operation:

- [ ] Family Composition section filled
- [ ] Loyalty Memberships section filled (or marked `—` for programs you don't have)
- [ ] Airline Preferences customized (especially Default avoid list)
- [ ] Budget Bands set to your range
- [ ] Visa Status set to current state
- [ ] Avoid List extended with personal preferences
- [ ] This file is **not** committed back to a public repo

Once filled, this profile drives every report — the more accurate the profile, the more useful the recommendations.
