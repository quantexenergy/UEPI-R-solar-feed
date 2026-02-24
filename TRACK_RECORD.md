# UEPI-R Track Record

Automated verification of UEPI-R alerts against [NOAA's official flare event list](https://services.swpc.noaa.gov/json/goes/primary/xray-flares-7-day.json).
Each alert is verified 24 hours after it fires. Git commit history proves every alert was published **before** the flare occurred.

## Summary

| Metric | Value |
|--------|-------|
| Verified hits | **7** |
| M-class coverage | **70.0%** (7/10 flares) |
| M-class hit rate | **26.9%** (7/26) |
| False alerts | 19/26 |
| Median lead time | **6h 34m** |
| Pending verification | 1 |
| Last updated | 2026-02-24T05:36:51Z |

## Event Log

```diff
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
*Generated automatically by [UEPI-R](https://github.com/quantexenergy) every 15 minutes.*
