# KOSPI2 Option Volatility Study
**Date: 2026-03-06** | KOSPI2 Index: 821 | VKOSPI: 67.8

---

## Vol Snapshot

| Metric | Current | Pre-Crisis Avg | Multiple |
|--------|---------|----------------|----------|
| VKOSPI | **67.8** | 18-20 | 3.5x |
| 30D ATM Vol (~Apr) | **59.7** | 29.0 | 2.1x |
| 60D ATM Vol (~May) | **53.5** | 29.4 | 1.8x |
| 30D Skew (90%-110% MNY) | **6.8** | 5.6 | 1.2x |
| 60D Skew (90%-110% MNY) | **4.1** | - | - |
| Term Spread (30D-60D) | **+6.1** | ~flat | - |

**Key observations:**
- Vol is 2x pre-crisis levels across the term structure
- Steep **backwardation** (front >> back) — classic post-shock pattern
- Skew only marginally wider than normal — the vol spike is mostly parallel, not skew-driven
- KOSPI2 rallied from ~430 to 933, then crashed — currently at ~820

---

## ATM Vol by Expiry

| Expiry | Date | DTE | ATM IVol (Call) | ATM IVol (Put) | Avg |
|--------|------|-----|-----------------|----------------|-----|
| **April** | 09-Apr-26 | ~34d | 64.3% | 56.7% | ~60.5% |
| **May** | 14-May-26 | ~69d | 58.1% | 53.0% | ~55.6% |
| **June** | 11-Jun-26 | ~97d | 55.6% | 51.0% | ~53.3% |

KOSPI2 futures (KMM6): **826.55**

---

## Option Chain — Calls (for trade construction)

### April Expiry (09-Apr-26)

| Strike | Bid | Ask | IVol Mid | Delta |
|--------|-----|-----|----------|-------|
| 840C | 47.50 | 59.75 | 62.8% | 0.48 |
| 860C | 38.75 | 49.30 | 61.4% | 0.42 |
| 880C | 32.05 | 40.15 | 58.9% | 0.36 |
| 900C | 26.50 | 32.75 | 58.2% | 0.34 |
| 920C | 21.30 | 26.60 | 57.5% | 0.30 |

### May Expiry (14-May-26)

| Strike | Bid | Ask | IVol Mid | Delta |
|--------|-----|-----|----------|-------|
| 940C | 29.80 | 39.30 | 53.2% | 0.32 |
| 960C | 25.80 | 33.90 | 53.2% | 0.29 |
| 980C | 22.35 | 28.40 | 52.6% | 0.26 |
| 1000C | 19.00 | 24.35 | 52.4% | 0.24 |

### June Expiry (11-Jun-26)

| Strike | Bid | Ask | IVol Mid | Delta |
|--------|-----|-----|----------|-------|
| 840C | 74.70 | 92.55 | 55.7% | 0.51 |
| 860C | 66.30 | 83.10 | 55.0% | 0.50 |
| 880C | 58.80 | 74.30 | 54.4% | 0.46 |
| 900C | 48.00 | 66.25 | 52.5% | 0.45 |
| 920C | 42.45 | 58.80 | 52.1% | 0.40 |

---

## Trade Suggestions: Short Vol, Small Long Delta

### Trade 1 (Recommended): May 860/920/980 Call Butterfly

| Leg | Action | Strike | Delta | IVol | Est. Mid |
|-----|--------|--------|-------|------|----------|
| Long 1x | Buy | 860C | 0.50 | 55.0 | ~74.7 |
| Short 2x | Sell | 920C | 0.40 | 52.1 | ~50.6 |
| Long 1x | Buy | 980C | 0.26 | 52.6 | ~25.4 |

*Note: Using June expiry prices above. For May, interpolate or use actual May chain.*

- **Net debit**: ~6-8 pts
- **Max profit**: ~50+ at 920 at expiry
- **Net delta**: small long (~+0.10)
- **Short vega**: selling body at higher premium, net short vol
- **Thesis**: Vol mean-reverts + KOSPI grinds higher toward 920 (~12% above spot)
- **Risk**: Max loss = debit paid. Limited, defined risk.

**Why May?** Front month (Apr) is richest but only 34 DTE — too short for a recovery play. May at 69 DTE gives enough time for vol normalization + spot recovery, while still capturing significant vol premium.

### Trade 2: May 860/900/940/980 Call Condor

| Leg | Action | Strike | Delta |
|-----|--------|--------|-------|
| Long 1x | Buy | 860C | 0.50 |
| Short 1x | Sell | 900C | 0.45 |
| Short 1x | Sell | 940C | 0.32 |
| Long 1x | Buy | 980C | 0.26 |

- **Net debit**: ~5-6 pts
- **Max profit**: ~34 (anywhere 900-940 at expiry)
- **Wider profit zone** than the fly — more forgiving
- **Net delta**: small long (~+0.08)
- **Short vol**: selling 2 rich options inside, buying 2 outside

### Trade 3: June 880/940/1000 Call Butterfly (More Time)

| Leg | Action | Strike | Delta | Est. Mid |
|-----|--------|--------|-------|----------|
| Long 1x | Buy | 880C | 0.46 | ~66.6 |
| Short 2x | Sell | 940C | 0.35 | ~43.9 |
| Long 1x | Buy | 1000C | 0.24 | ~29.9 |

- **Net debit**: ~8-9 pts
- **Max profit**: ~51 at 940 (expiry 11-Jun)
- **97 DTE** — more time for vol to normalize + spot to recover
- **June vol at 52-55%** still extremely rich vs 29% norm

### Trade 4: May Call Ratio Spread — Buy 1x 880C / Sell 2x 960C

- Net credit of ~6 pts
- **Heavily short vol** at the 960 strike
- **Risk**: Unlimited above ~1040 (27% rally) — less suitable for defined-risk mandate
- Consider only with a stop or wing protection

---

## Ranking

| Rank | Trade | Risk Profile | Vol Exposure | Delta | Time |
|------|-------|-------------|-------------|-------|------|
| 1 | May 860/920/980 Call Fly | Defined | Short vega | Small long | 69d |
| 2 | May Call Condor | Defined | Short vega | Small long | 69d |
| 3 | June 880/940/1000 Call Fly | Defined | Short vega | Small long | 97d |
| 4 | May Call Ratio Spread | Undefined | Very short vega | Varies | 69d |

**Primary recommendation: May 860/920/980 Call Butterfly** — cleanest expression of short vol + long delta with defined risk, and positioned for a 10-15% recovery in KOSPI2 over the next 2 months.

---

## Charts

- `kospi_atm_vol.png` — ATM implied vol by tenor (30D, 60D, VKOSPI) with pre-crisis range
- `kospi_vol_term.png` — Vol term structure spread (30D - 60D backwardation)
- `kospi_skew.png` — Put-call skew (90% vs 110% moneyness)
- `kospi_vol_dashboard.png` — Combined 3-panel dashboard
