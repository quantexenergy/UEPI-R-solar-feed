# UEPI-R Solar Flare Early Warning

> **QUIET** — No elevated flare risk detected.

*Last updated: 2026-02-10 00:01 UTC*

---

## Verified Track Record

Every alert is automatically verified against [NOAA's official flare event list](https://services.swpc.noaa.gov/json/goes/primary/xray-flares-7-day.json) after 24 hours.
Git commit history proves each alert was published **before** the flare occurred.

| Metric | Value |
|--------|-------|
| M-class hit rate | **100.0%** (2/2) |
| False alerts | 0/2 |
| Median lead time | **11h 57m** |

```diff
+ HIT  Alert: 2026-02-08 11:26 UTC  |  Flare: M2.7 at 2026-02-08 13:46 UTC  |  Lead: 2h 20m
+ HIT  Alert: 2026-02-08 04:39 UTC  |  Flare: M2.8 at 2026-02-09 02:14 UTC  |  Lead: 21h 35m
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
