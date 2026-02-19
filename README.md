# UEPI-R Solar Flare Early Warning

> **RED ALERT** — Elevated solar flare risk detected. An M1.0+ flare is likely within the next 2-24 hours.

*Last updated: 2026-02-19 21:03 UTC*

---

## Verified Track Record

Every alert is automatically verified against [NOAA's official flare event list](https://services.swpc.noaa.gov/json/goes/primary/xray-flares-7-day.json) after 24 hours.
Git commit history proves each alert was published **before** the flare occurred.

| Metric | Value |
|--------|-------|
| Verified hits | **7** |
| M-class coverage | **70.0%** (7/10 flares) |
| M-class hit rate | **38.9%** (7/18) |
| False alerts | 11/18 |
| Median lead time | **6h 34m** |
| Pending | 2 |

```diff
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

## About UEPI-R

UEPI-R is a causal regime detection system that monitors NOAA GOES X-ray satellite data in real time
and identifies solar instability conditions **before** major solar flares (M1.0+) occur.

- **Causal** — No future data used. Strictly real-time compatible.
- **Automated** — Runs every 15 minutes via GitHub Actions.
- **Verified** — Every alert is cross-referenced against NOAA's official flare event list.

### Backtested Performance (2010-2025)

Validated on 16 years of NOAA/GOES XRS data:

| Metric | Value |
|--------|-------|
| X-class coverage | 97.2% (137/141) |
| M-class coverage | 69.5% |
| Precision | 39.6% |
| False alerts | 0.36/day |
| Median lead time | ~6 hours |

---

## Data Files

| File | Description |
|------|-------------|
| [`uepi_r_public.json`](uepi_r_public.json) | Current alert state |
| [`uepi_r_public_transitions.json`](uepi_r_public_transitions.json) | Recent alert transitions |
| [`verified_scorecard.json`](verified_scorecard.json) | Verification statistics |
| [`TRACK_RECORD.md`](TRACK_RECORD.md) | Full alert log with verification |
| [`history/transitions.jsonl`](history/transitions.jsonl) | Complete transition history |
| [`history/verified.jsonl`](history/verified.jsonl) | Complete verification log |

## Quick Start

```bash
# Check current status
curl -s https://raw.githubusercontent.com/quantexenergy/UEPI-R-solar-feed/main/uepi_r_public.json | python3 -m json.tool
```

---

**Data source:** [NOAA GOES X-Ray Sensor (XRS)](https://www.swpc.noaa.gov/products/goes-x-ray-flux) — GOES-16/17/18 satellites

**Patent:** US Provisional Application No. 63/949,419 (December 28, 2025)

**[Quantex Energy](https://github.com/quantexenergy)**
