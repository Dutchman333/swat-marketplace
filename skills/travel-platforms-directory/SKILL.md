---
name: travel-platforms-directory
version: "1.0.0"
description: Travel booking and price-comparison platform registry — domestic vs international OTAs, airline aggregators, hotel direct-booking sites, and a category-to-platform decision tree
---

# Travel Platforms Directory

A maintained registry of travel booking platforms with strengths, gotchas, and a decision tree for which to query in any given task.

## Use When

- Selecting which platforms to query for hotel / flight / package research
- Cross-checking a quoted price against alternative sources
- Routing a price-comparison subtask

## Hotel Platforms

### Domestic (Chinese OTAs)

| Platform | Strength | Gotcha |
|---|---|---|
| **携程 (Ctrip / Trip.com CN)** | Largest domestic inventory; Chinese customer support; price-match common | International rates often higher than overseas OTAs; some hotels list only in CNY |
| **飞猪 (Fliggy)** | Alibaba ecosystem; strong promo cycles (88VIP, 双 11); hotel package + flight bundles | UI/UX inconsistency; smaller international inventory |
| **去哪儿 (Qunar)** | Aggregator behind Ctrip; price comparison tool | Owned by Trip.com Group — same inventory as Ctrip with different UI |
| **美团 (Meituan)** | Domestic city hotels; same-day booking; lifestyle integration | Limited international; mostly mid-tier domestic |

### International OTAs

| Platform | Strength | Gotcha |
|---|---|---|
| **Booking.com** | Largest global inventory; pay-at-hotel option common; flexible cancellation | Customer-service slow on disputes; sometimes the "lowest" rate has hidden city tax |
| **Agoda** | **Strongest in Asia** (Japan, Korea, Thailand, Vietnam, Indonesia); aggressive Asia promos | Owned by Booking Holdings; UI shows pre-tax pricing — always check final |
| **Trip.com** | Strong on flight + hotel combo; transit visa expertise; multi-currency display | Sometimes higher than Ctrip CN for the same property; check both |
| **Hotels.com** | "Stay 10 nights, get 1 free" loyalty (legacy) | Inventory shrinking; sometimes lacks newer properties |
| **Expedia** | Bundle discounts (flight+hotel+car); decent rewards | Better for North America; weaker in Asia |
| **Klook / KKday** | Asia-focused activities + select hotels | Mostly experiences, not the strongest hotel pricing |

### Direct Booking (Highest Priority for Loyalty)

| Site | Why it matters |
|---|---|
| **IHG.com** | If you hold IHG One Rewards status (see `personal-travel-profile`), direct booking is required to apply benefits — Ambassador tier unlocks: complimentary upgrade subject to availability, weekend benefit, free breakfast at InterContinental, 4 PM late checkout, BOGO at IC, double IHG One Rewards points, status-match opportunities. Always check direct rate vs OTA — if within 10%, choose direct. |
| **Marriott.com** | If you (or spouse) hold Marriott Bonvoy status, direct booking is required to apply benefits — Gold = 25% bonus points + 2 PM late checkout + room upgrade subject to availability + enhanced internet; Platinum+ adds breakfast and lounge access. Same 10% rule as IHG. |
| **Hilton / Hyatt / Accor / Shangri-La direct** | Same logic if any property is in those chains — direct rate often matches OTA + adds member perks. |

### Hotel Comparison Discipline

For every hotel recommendation:

```
| 平台 | 房型 | 含税总价 (CNY) | 是否含早 | 取消政策 | 会员权益 | 链接 |
|------|------|----------------|----------|----------|----------|------|
| 携程 | ... | ¥X | ✓ | 灵活取消 | — | url |
| Booking | ... | ¥X | ✗ | 灵活取消 | — | url |
| Agoda | ... | ¥X | ✗ | 不可取消 | — | url |
| IHG.com | ... | ¥X | ✓ | 灵活取消 | Ambassador 升舱 + 4PM 退房 + 早餐 | url |
```

Then a 1-line conclusion: which to book and why.

## Flight Platforms

### Aggregators (Discovery)

| Platform | Strength | Gotcha |
|---|---|---|
| **Skyscanner** | Best for "anywhere" / "any month" exploration; transparent multi-stop options | Doesn't always show airline direct; final price may differ at checkout |
| **Google Flights** | Best price-history graph and date-grid; honest about which OTA / airline owns the price | Limited China-domestic coverage |
| **Kiwi.com** | Hidden-city / multi-leg / virtual interlining specialist; can save 30-50% on complex routes | Self-transfer = no airline protection; only use if buyer accepts that risk |
| **携程 / 飞猪 国际机票** | Chinese language, CNY billing, sometimes special low-cost contracts | Hard sell of insurance / lounge / fast-track |

### Airline Direct (Best for 5-star Carriers)

Operator's preferred 5-star airlines (sorted by typical product strength):

| Airline | Why preferred | Booking site |
|---|---|---|
| **Singapore Airlines (SQ)** | A380 suites, A350 J product, Krisflyer alliance | singaporeair.com |
| **Cathay Pacific (CX)** | HK hub, J product, OneWorld | cathaypacific.com |
| **ANA / JAL** | Japan service, Star Alliance / OneWorld | ana.co.jp / jal.com |
| **Qatar Airways (QR)** | Qsuite J, Doha hub | qatarairways.com |
| **Emirates (EK)** | A380 onboard bar, shower, Dubai hub | emirates.com |
| **EVA Air (BR)** | Hello Kitty themed cabin, TPE hub, well-rated J | evaair.com |
| **Lufthansa / Swiss / Turkish** | European 5-star fallback | lh.com / swiss.com / turkishairlines.com |

### Chinese Mainland Carriers — Default Avoid

Air China / China Eastern / China Southern / Hainan / Spring etc. are **default avoid** unless:

- They are the **only carrier** on a needed route, or
- Their schedule beats foreign carriers by >= 3 hours saved, **and**
- Their fare is >= 50% cheaper than the foreign alternative.

If recommended, state the trade-off explicitly in a "tradeoff" callout.

### Flight Comparison Discipline

For every recommended flight option:

```
| 平台 | 航班号 | 路线 | 总时长 | 中转 | 含税总价 (CNY) | 行李 | 退改 | 链接 |
|------|--------|------|--------|------|----------------|------|------|------|
| Google Flights | SQ 833 + SQ 12 | PEK-SIN-LAX | 22h | 1 stop, SIN 2h | ¥X | 2x32kg | 改签 ¥X | url |
| Skyscanner | 同上 | ... | ... | ... | ¥X | ... | ... | url |
| singaporeair.com | 同上 | ... | ... | ... | ¥X | + KrisFlyer 里程 + 升舱选项 | ... | url |
```

## Restaurant / Activity Platforms

| Platform | Use for |
|---|---|
| **OpenTable / TheFork / Tabelog (Japan)** | Reservations |
| **Tripadvisor** | Restaurant + attraction reviews (with skepticism) |
| **Klook / KKday / GetYourGuide** | Tickets, day tours, transfers |
| **小红书 / 大众点评** | Real Chinese-traveler reviews — best for hidden gems |

## Decision Tree

```
Hotel?
├─ Domestic destination → 携程 + 飞猪 + 直订（如属 IHG/Marriott）+ Booking 比对
└─ International destination
    ├─ Asia (especially Japan/SE Asia) → Agoda + Booking + Trip.com + 直订
    └─ Europe / Americas → Booking + Trip.com + 直订 + 携程 比对

Flight?
├─ Discovery / "anywhere" → Skyscanner + Google Flights
├─ Specific route, single airline → airline direct (5-star) + Google Flights cross-check
└─ Multi-leg / open-jaw → Kiwi.com (only if accept self-transfer risk) + Skyscanner

Activity / restaurant?
├─ Reserved restaurant → OpenTable / TheFork / Tabelog
├─ Real reviews → 小红书 + Tripadvisor (cross-check)
└─ Tickets / tours → Klook / KKday + 直订
```

## Coverage Rule (matches squad rule #2 and #3)

- Hotel: >= 2 domestic + >= 2 international + direct (if loyalty applicable) — minimum 5 sources for any recommendation
- Flight: aggregator + aggregator + airline direct — minimum 3 sources
- Restaurant: reservation platform + review platform — minimum 2 sources
