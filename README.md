# UEPI-R Solar Flare Risk Monitor

Continuous M/X-Class Flare Risk Assessment (GOES XRS Only)

```
2026-04-09 21:15 UTC | Status: QUIET | P(M1.0+ within 24h): 7.5%
```

---

## Scientific Validation

Castillo, A. (2026). *UEPI-R: Real-Time Early Warning for M- and X-Class Solar Flares Using Causal Regime Detection on GOES XRS Data.*
DOI: [10.22541/essoar.177177373.33605226/v1](https://doi.org/10.22541/essoar.177177373.33605226/v1)

Validated on 16 years (2010-2025) of NOAA GOES XRS data.

| Metric | Value |
|--------|-------|
| X-class detection | **97.2%** (137/141) |
| M/X detection | 64-71% (matching dependent) |
| Precision | 39.6% |
| False alert rate | 0.36/day |
| Day-level TSS | 0.69 |
| Brier skill score | 0.38 (calibrated probability) |

UEPI-R identifies elevated flare-risk periods using causal regime detection on GOES XRS flux. During active periods, the system maintains elevated risk state and calibrated probability output. It is not a point-in-time onset predictor.

---

## Live Operational Track Record

All alerts are automatically verified against [NOAA's official flare list](https://services.swpc.noaa.gov/json/goes/primary/xray-flares-7-day.json) after a 24-hour hazard window.

A baseline-window bug inflated false alerts before March 21, 2026 (see note below).
The **Since Fix** column reflects corrected performance.

| Metric | Lifetime | Since Fix (Mar 21) |
|--------|:--------:|:------------------:|
| M-class coverage | 71.4% (15/21) | **77.8%** (7/9) |
| Precision | 20.5% | **41.2%** |
| False alerts/day | 0.98 | **0.60** |
| Median lead time | 11.5h | **12.1h** |
| Alerts | 73 | 17 |
| Pending | 1 | |

### Verification Rules

- **Flare threshold:** GOES class >= M1.0 (NOAA classification)
- **Hazard window:** 24 hours from alert onset
- **Hit:** First >= M1.0 flare within hazard window
- **False alert:** No >= M1.0 flare within 24h
- **Miss:** Flare with no active alert at onset
- **Pending:** Hazard window not yet expired

All alerts are timestamped via Git commits prior to flare occurrence.

Full log: [`TRACK_RECORD.md`](TRACK_RECORD.md)

```diff
! C-ASSOCIATED Alert: 2026-04-08 15:52 UTC  |  No M1.0+ (C1.4 at 23:38)
! C-ASSOCIATED Alert: 2026-04-07 18:34 UTC  |  No M1.0+ (C8.7 at 15:31)
+ HIT  Alert: 2026-04-04 19:51 UTC  |  Flare: M1.0 at 2026-04-04 22:54 UTC  |  Lead: 3h 02m
+ HIT  Alert: 2026-04-04 08:00 UTC  |  Flare: M1.2 at 2026-04-04 11:58 UTC  |  Lead: 3h 57m
+ HIT  Alert: 2026-04-03 19:30 UTC  |  Flare: M1.7 at 2026-04-04 07:38 UTC  |  Lead: 12h 07m
+ HIT  Alert: 2026-04-03 06:00 UTC  |  Flare: M7.5 at 2026-04-04 01:07 UTC  |  Lead: 19h 06m
+ HIT  Alert: 2026-04-03 01:15 UTC  |  Flare: M1.3 at 2026-04-03 12:46 UTC  |  Lead: 11h 30m
+ HIT  Alert: 2026-04-02 18:15 UTC  |  Flare: M1.3 at 2026-04-03 07:45 UTC  |  Lead: 13h 29m
+ HIT  Alert: 2026-04-01 20:15 UTC  |  Flare: M3.5 at 2026-04-02 17:23 UTC  |  Lead: 21h 07m
! C-ASSOCIATED Alert: 2026-04-01 13:57 UTC  |  No M1.0+ (C8.1 at 19:47)
! C-ASSOCIATED Alert: 2026-03-30 03:15 UTC  |  No M1.0+ (C2.1 at 20:40)
! MISS Flare: X1.4 at 2026-03-30 02:47 UTC  |  No alert issued
! C-ASSOCIATED Alert: 2026-03-28 03:15 UTC  |  No M1.0+ (C4.1 at 11:18)
! C-ASSOCIATED Alert: 2026-03-27 10:05 UTC  |  No M1.0+ (C3.5 at 18:17)
! C-ASSOCIATED Alert: 2026-03-26 06:30 UTC  |  No M1.0+ (C3.6 at 02:55)
! MISS Flare: M3.9 at 2026-03-26 06:11 UTC  |  No alert issued
! C-ASSOCIATED Alert: 2026-03-25 00:30 UTC  |  No M1.0+ (C2.2 at 04:10)
! C-ASSOCIATED Alert: 2026-03-24 17:45 UTC  |  No M1.0+ (C3.7 at 00:14)
! C-ASSOCIATED Alert: 2026-03-23 00:00 UTC  |  No M1.0+ (C3.2 at 00:24)
! C-ASSOCIATED Alert: 2026-03-18 08:45 UTC  |  No M1.0+ (C3.6 at 12:53)
! C-ASSOCIATED Alert: 2026-03-18 01:25 UTC  |  No M1.0+ (C3.6 at 12:53)
! C-ASSOCIATED Alert: 2026-03-16 12:15 UTC  |  No M1.0+ (C5.9 at 14:39)
! MISS Flare: M2.7 at 2026-03-16 12:00 UTC  |  No alert issued
! C-ASSOCIATED Alert: 2026-03-15 10:00 UTC  |  No M1.0+ (C1.1 at 15:00)
! C-ASSOCIATED Alert: 2026-03-13 20:30 UTC  |  No M1.0+ (C7.4 at 20:33)
! C-ASSOCIATED Alert: 2026-03-13 15:27 UTC  |  No M1.0+ (C8.9 at 20:09)
! C-ASSOCIATED Alert: 2026-03-13 06:02 UTC  |  No M1.0+ (C8.9 at 20:09)
! C-ASSOCIATED Alert: 2026-03-12 08:45 UTC  |  No M1.0+ (C4.3 at 00:57)
! C-ASSOCIATED Alert: 2026-03-10 19:00 UTC  |  No M1.0+ (C1.1 at 00:56)
! C-ASSOCIATED Alert: 2026-03-09 20:45 UTC  |  No M1.0+ (C4.6 at 18:32)
- FALSE Alert: 2026-03-04 05:34 UTC  |  No M1.0+ flare within 24h
! C-ASSOCIATED Alert: 2026-03-03 16:51 UTC  |  No M1.0+ (C4.1 at 02:57)
! C-ASSOCIATED Alert: 2026-03-03 10:04 UTC  |  No M1.0+ (C4.1 at 02:57)
! C-ASSOCIATED Alert: 2026-03-03 01:22 UTC  |  No M1.0+ (C2.0 at 15:45)
! C-ASSOCIATED Alert: 2026-03-02 08:56 UTC  |  No M1.0+ (C2.9 at 10:22)
! C-ASSOCIATED Alert: 2026-03-02 04:56 UTC  |  No M1.0+ (C2.9 at 10:22)
! C-ASSOCIATED Alert: 2026-03-01 22:10 UTC  |  No M1.0+ (C4.5 at 04:29)
! C-ASSOCIATED Alert: 2026-03-01 17:16 UTC  |  No M1.0+ (C4.5 at 04:29)
! C-ASSOCIATED Alert: 2026-03-01 09:38 UTC  |  No M1.0+ (C4.5 at 04:29)
! C-ASSOCIATED Alert: 2026-03-01 02:22 UTC  |  No M1.0+ (C5.9 at 07:30)
! C-ASSOCIATED Alert: 2026-02-28 21:38 UTC  |  No M1.0+ (C6.1 at 01:55)
! C-ASSOCIATED Alert: 2026-02-28 09:42 UTC  |  No M1.0+ (C6.1 at 01:55)
! C-ASSOCIATED Alert: 2026-02-28 03:32 UTC  |  No M1.0+ (C6.1 at 01:55)
! C-ASSOCIATED Alert: 2026-02-27 19:53 UTC  |  No M1.0+ (C3.4 at 19:59)
! C-ASSOCIATED Alert: 2026-02-27 09:29 UTC  |  No M1.0+ (C3.5 at 12:46)
! C-ASSOCIATED Alert: 2026-02-26 19:24 UTC  |  No M1.0+ (C3.5 at 12:46)
! C-ASSOCIATED Alert: 2026-02-26 09:21 UTC  |  No M1.0+ (C6.3 at 18:56)
- FALSE Alert: 2026-02-25 15:59 UTC  |  No M1.0+ flare within 24h
+ HIT  Alert: 2026-02-25 05:27 UTC  |  Flare: M2.3 at 2026-02-25 15:35 UTC  |  Lead: 10h 07m
- FALSE Alert: 2026-02-23 11:53 UTC  |  No M1.0+ flare within 24h
- FALSE Alert: 2026-02-22 07:06 UTC  |  No M1.0+ flare within 24h
! C-ASSOCIATED Alert: 2026-02-22 01:47 UTC  |  No M1.0+ (C2.2 at 06:20)
! C-ASSOCIATED Alert: 2026-02-21 09:56 UTC  |  No M1.0+ (C2.2 at 06:20)
! C-ASSOCIATED Alert: 2026-02-21 04:53 UTC  |  No M1.0+ (C1.2 at 00:26)
- FALSE Alert: 2026-02-20 14:24 UTC  |  No M1.0+ flare within 24h
- FALSE Alert: 2026-02-20 05:07 UTC  |  No M1.0+ flare within 24h
! C-ASSOCIATED Alert: 2026-02-19 19:53 UTC  |  No M1.0+ (C2.9 at 02:52)
! C-ASSOCIATED Alert: 2026-02-19 07:55 UTC  |  No M1.0+ (C2.9 at 02:52)
! C-ASSOCIATED Alert: 2026-02-18 20:03 UTC  |  No M1.0+ (C2.2 at 20:17)
! C-ASSOCIATED Alert: 2026-02-18 00:00 UTC  |  No M1.0+ (C2.2 at 20:17)
! C-ASSOCIATED Alert: 2026-02-17 18:08 UTC  |  No M1.0+ (C1.8 at 23:07)
! C-ASSOCIATED Alert: 2026-02-17 10:32 UTC  |  No M1.0+ (C1.8 at 23:07)
! C-ASSOCIATED Alert: 2026-02-17 05:14 UTC  |  No M1.0+ (C1.8 at 23:07)
! C-ASSOCIATED Alert: 2026-02-16 14:13 UTC  |  No M1.0+ (C1.0 at 04:43)
- FALSE Alert: 2026-02-15 21:49 UTC  |  No M1.0+ flare within 24h
+ HIT  Alert: 2026-02-15 08:02 UTC  |  Flare: M2.4 at 2026-02-16 04:03 UTC  |  Lead: 20h
! C-ASSOCIATED Alert: 2026-02-14 11:45 UTC  |  No M1.0+ (C1.2 at 07:19)
! C-ASSOCIATED Alert: 2026-02-13 11:49 UTC  |  No M1.0+ (C6.0 at 11:02)
- FALSE Alert: 2026-02-13 00:00 UTC  |  No M1.0+ flare within 24h
+ HIT  Alert: 2026-02-12 18:10 UTC  |  Flare: M1.0 at 2026-02-13 08:28 UTC  |  Lead: 14h 17m
+ HIT  Alert: 2026-02-11 13:00 UTC  |  Flare: M1.4 at 2026-02-12 02:29 UTC  |  Lead: 13h 29m
+ HIT  Alert: 2026-02-11 07:50 UTC  |  Flare: M1.4 at 2026-02-11 12:47 UTC  |  Lead: 4h 57m
! MISS Flare: M1.3 at 2026-02-11 00:50 UTC  |  No alert issued
! MISS Flare: M1.1 at 2026-02-11 00:29 UTC  |  No alert issued
! MISS Flare: M1.2 at 2026-02-10 23:56 UTC  |  No alert issued
! C-ASSOCIATED Alert: 2026-02-09 18:17 UTC  |  No M1.0+ (C9.2 at 22:53)
+ HIT  Alert: 2026-02-09 01:57 UTC  |  Flare: M2.8 at 2026-02-09 02:14 UTC  |  Lead: 17min
+ HIT  Alert: 2026-02-08 11:26 UTC  |  Flare: M1.7 at 2026-02-08 11:32 UTC  |  Lead: 6min
+ HIT  Alert: 2026-02-08 04:39 UTC  |  Flare: M1.8 at 2026-02-08 11:13 UTC  |  Lead: 6h 34m
```

---

## What UEPI-R Does

UEPI-R monitors GOES XRS irradiance to identify periods of elevated solar flare risk.

- Detects elevated-risk regimes from XRS flux alone (no magnetograms)
- Fully causal (no future data)
- Calibrated P(M1.0+ within 24h) updated every 15 minutes
- Binary risk flag (`red_alert`) for automated downstream triggers
- 97% of X-class flares in 2010-2025 occurred during flagged risk periods

Runs automatically every 15 minutes via GitHub Actions.

## Probability Interpretation

The climatological base rate is ~20%: roughly one in five 15-minute samples falls within 24 hours of an M1.0+ flare. Probabilities are isotonically calibrated against 2010-2025 GOES data (Brier skill score 0.38).

| P(M1.0+ 24h) | Level | Backtest observed rate | Time in tier |
|---|---|---|---|
| < 5% | Low | ~2% | ~54% |
| 5-20% | Elevated | ~10% | ~10% |
| 20-50% | Moderate | ~30% | ~21% |
| 50-80% | High | ~65% | ~11% |
| > 80% | Very High | ~90% | ~4% |

- The 20% base rate means "Moderate" starts at above-average risk.
- `red_alert: true` typically corresponds to probabilities above 20-30%.
- Probabilities are calibrated: a 40% reading means ~40% of similar moments in 2010-2025 were followed by an M1.0+ flare within 24 hours.

**`red_alert` vs `flare_probability`:** The probability reflects overall environmental risk (dominated by background flux level). The `red_alert` flag triggers when the system detects an elevated-risk regime (rising flux + spectral hardening + sustained activity). During active periods, `red_alert` may remain true for hours to days. The probability provides finer granularity within that risk window.

---

## API Access

```bash
curl -s https://raw.githubusercontent.com/quantexenergy/UEPI-R-solar-feed/main/uepi_r_public.json
```

| File | Description |
|------|-------------|
| [`uepi_r_public.json`](uepi_r_public.json) | Current alert state |
| [`uepi_r_public_transitions.json`](uepi_r_public_transitions.json) | Recent transitions |
| [`verified_scorecard.json`](verified_scorecard.json) | Live verification stats |
| [`history/transitions.jsonl`](history/transitions.jsonl) | Full alert history |
| [`history/verified.jsonl`](history/verified.jsonl) | Full verification log |

---

**Data source:** [NOAA GOES X-Ray Sensor (XRS)](https://www.swpc.noaa.gov/products/goes-x-ray-flux) — GOES-16/17/18 satellites

**Intellectual Property:** U.S. Provisional Application No. 63/949,419 (Dec 28, 2025)

**[Quantex Energy](https://github.com/quantexenergy)**
