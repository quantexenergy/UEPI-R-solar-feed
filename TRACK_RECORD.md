# UEPI-R Track Record

Automated verification of UEPI-R alerts against [NOAA's official flare event list](https://services.swpc.noaa.gov/json/goes/primary/xray-flares-7-day.json).
Each alert is verified 24 hours after it fires. Git commit history proves every alert was published **before** the flare occurred.

## Summary

| Metric | Value |
|--------|-------|
| Verified hits | **2** |
| M-class hit rate | **50.0%** (2/4) |
| False alerts | 2/4 |
| Median lead time | **11h 57m** |
| Last updated | 2026-02-11T14:40:35Z |

## Alert Log

```diff
- MISS Alert: 2026-02-09 18:17 UTC  |  No M1.0+ flare within 24h
- MISS Alert: 2026-02-09 01:57 UTC  |  No M1.0+ flare within 24h
+ HIT  Alert: 2026-02-08 11:26 UTC  |  Flare: M2.7 at 2026-02-08 13:46 UTC  |  Lead: 2h 20m
+ HIT  Alert: 2026-02-08 04:39 UTC  |  Flare: M2.8 at 2026-02-09 02:14 UTC  |  Lead: 21h 35m
```

---
*Generated automatically by [UEPI-R](https://github.com/quantexenergy) every 15 minutes.*
