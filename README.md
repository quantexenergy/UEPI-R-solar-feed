# UEPI-R Solar Flare Early Warning

Real-Time M/X-Class Flare Onset Detection (GOES XRS Only)

```
2026-02-27 14:29 UTC | Status: QUIET | P(M1.0+ within 24h): 28.8%
```

---

## Scientific Validation

Castillo, A. (2026). *UEPI-R: Real-Time Early Warning for M- and X-Class Solar Flares Using Causal Regime Detection on GOES XRS Data.*
DOI: [10.22541/essoar.177177373.33605226/v1](https://doi.org/10.22541/essoar.177177373.33605226/v1)

Validated on 16 years (2010-2025) of NOAA GOES XRS data.

| Metric | Value |
|--------|-------|
| X-class coverage | **97.2%** (137/141) |
| M/X coverage | 64-71% (matching dependent) |
| Precision | 39.6% |
| False alert rate | 0.36/day |
| Day-level TSS | 0.41 |
| Median lead time | 2.4-4.3 hours |

UEPI-R is a continuous onset-warning system, not a 24-hour binary classifier.

---

## Live Operational Track Record

All alerts are automatically verified against [NOAA's official flare list](https://services.swpc.noaa.gov/json/goes/primary/xray-flares-7-day.json) after a 24-hour hazard window.

| Metric | Value |
|--------|-------|
| Verified hits | **8** |
| Total M1.0+ flares | 11 |
| Coverage | **72.7%** |
| Precision | 8/30 alerts (26.7%) |
| False alerts | 22 |
| Median lead time | **8h 20m** |
| Pending | 2 |

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
- FALSE Alert: 2026-02-26 09:21 UTC  |  No M1.0+ flare within 24h
- FALSE Alert: 2026-02-25 15:59 UTC  |  No M1.0+ flare within 24h
+ HIT  Alert: 2026-02-25 05:27 UTC  |  Flare: M2.3 at 2026-02-25 15:35 UTC  |  Lead: 10h 07m
- FALSE Alert: 2026-02-23 11:53 UTC  |  No M1.0+ flare within 24h
- FALSE Alert: 2026-02-22 07:06 UTC  |  No M1.0+ flare within 24h
- FALSE Alert: 2026-02-22 01:47 UTC  |  No M1.0+ flare within 24h
- FALSE Alert: 2026-02-21 09:56 UTC  |  No M1.0+ flare within 24h
- FALSE Alert: 2026-02-21 04:53 UTC  |  No M1.0+ flare within 24h
- FALSE Alert: 2026-02-20 14:24 UTC  |  No M1.0+ flare within 24h
- FALSE Alert: 2026-02-20 05:07 UTC  |  No M1.0+ flare within 24h
- FALSE Alert: 2026-02-19 19:53 UTC  |  No M1.0+ flare within 24h
- FALSE Alert: 2026-02-19 07:55 UTC  |  No M1.0+ flare within 24h
- FALSE Alert: 2026-02-18 20:03 UTC  |  No M1.0+ flare within 24h
- FALSE Alert: 2026-02-18 00:00 UTC  |  No M1.0+ flare within 24h
- FALSE Alert: 2026-02-17 18:08 UTC  |  No M1.0+ flare within 24h
- FALSE Alert: 2026-02-17 10:32 UTC  |  No M1.0+ flare within 24h
- FALSE Alert: 2026-02-17 05:14 UTC  |  No M1.0+ flare within 24h
- FALSE Alert: 2026-02-16 14:13 UTC  |  No M1.0+ flare within 24h
- FALSE Alert: 2026-02-15 21:49 UTC  |  No M1.0+ flare within 24h
+ HIT  Alert: 2026-02-15 08:02 UTC  |  Flare: M2.4 at 2026-02-16 04:03 UTC  |  Lead: 20h
- FALSE Alert: 2026-02-14 11:45 UTC  |  No M1.0+ flare within 24h
- FALSE Alert: 2026-02-13 11:49 UTC  |  No M1.0+ flare within 24h
- FALSE Alert: 2026-02-13 00:00 UTC  |  No M1.0+ flare within 24h
+ HIT  Alert: 2026-02-12 18:10 UTC  |  Flare: M1.0 at 2026-02-13 08:28 UTC  |  Lead: 14h 17m
+ HIT  Alert: 2026-02-11 13:00 UTC  |  Flare: M1.4 at 2026-02-12 02:29 UTC  |  Lead: 13h 29m
+ HIT  Alert: 2026-02-11 07:50 UTC  |  Flare: M1.4 at 2026-02-11 12:47 UTC  |  Lead: 4h 57m
! MISS Flare: M1.3 at 2026-02-11 00:50 UTC  |  No alert issued
! MISS Flare: M1.1 at 2026-02-11 00:29 UTC  |  No alert issued
! MISS Flare: M1.2 at 2026-02-10 23:56 UTC  |  No alert issued
- FALSE Alert: 2026-02-09 18:17 UTC  |  No M1.0+ flare within 24h
+ HIT  Alert: 2026-02-09 01:57 UTC  |  Flare: M2.8 at 2026-02-09 02:14 UTC  |  Lead: 17min
+ HIT  Alert: 2026-02-08 11:26 UTC  |  Flare: M1.7 at 2026-02-08 11:32 UTC  |  Lead: 6min
+ HIT  Alert: 2026-02-08 04:39 UTC  |  Flare: M1.8 at 2026-02-08 11:13 UTC  |  Lead: 6h 34m
```

---

## What UEPI-R Does

UEPI-R performs causal regime detection on full-disk GOES XRS irradiance data.

- XRS-only input (no magnetograms)
- Fully causal (no future data)
- Continuous minute-resolution alerting
- Multi-tier alert states
- Logistic-calibrated probability output (Brier score: 0.098)

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
