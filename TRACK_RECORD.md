# UEPI-R Track Record

Automated verification of UEPI-R alerts against [NOAA's official flare event list](https://services.swpc.noaa.gov/json/goes/primary/xray-flares-7-day.json).
Each alert is verified 24 hours after it fires. Git commit history proves every alert was published **before** the flare occurred.

## Summary

| Metric | Value |
|--------|-------|
| Verified hits | **6** |
| M-class hit rate | **66.7%** (6/9) |
| False alerts | 3/9 |
| Median lead time | **5h 45m** |
| Pending verification | 1 |
| Last updated | 2026-02-15T07:29:10Z |

## Alert Log

```diff
- FALSE Alert: 2026-02-13 11:49 UTC  |  No M1.0+ flare within 24h
- FALSE Alert: 2026-02-13 00:00 UTC  |  No M1.0+ flare within 24h
+ HIT  Alert: 2026-02-12 18:10 UTC  |  Flare: M1.0 at 2026-02-13 08:28 UTC  |  Lead: 14h 17m
+ HIT  Alert: 2026-02-11 13:00 UTC  |  Flare: M1.4 at 2026-02-12 02:29 UTC  |  Lead: 13h 29m
+ HIT  Alert: 2026-02-11 07:50 UTC  |  Flare: M1.4 at 2026-02-11 12:47 UTC  |  Lead: 4h 57m
- FALSE Alert: 2026-02-09 18:17 UTC  |  No M1.0+ flare within 24h
+ HIT  Alert: 2026-02-09 01:57 UTC  |  Flare: M2.8 at 2026-02-09 02:14 UTC  |  Lead: 17min
+ HIT  Alert: 2026-02-08 11:26 UTC  |  Flare: M1.7 at 2026-02-08 11:32 UTC  |  Lead: 6min
+ HIT  Alert: 2026-02-08 04:39 UTC  |  Flare: M1.8 at 2026-02-08 11:13 UTC  |  Lead: 6h 34m
```

---
*Generated automatically by [UEPI-R](https://github.com/quantexenergy) every 15 minutes.*
