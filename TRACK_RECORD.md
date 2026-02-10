# UEPI-R Track Record

Automated verification of UEPI-R alerts against [NOAA's official flare event list](https://services.swpc.noaa.gov/json/goes/primary/xray-flares-7-day.json).
Each alert is verified 24 hours after it fires. Git commit history proves every alert was published **before** the flare occurred.

## Summary

| Metric | Value |
|--------|-------|
| Verified hits | **2** |
| False alerts | 0 |
| Hit rate | **100.0%** |
| Median lead time | **11h 57m** |
| Last updated | 2026-02-10T05:36:44Z |

## Alert Log

```diff
+ HIT  Alert: 2026-02-08 11:26 UTC  |  Flare: M2.7 at 2026-02-08 13:46 UTC  |  Lead: 2h 20m
+ HIT  Alert: 2026-02-08 04:39 UTC  |  Flare: M2.8 at 2026-02-09 02:14 UTC  |  Lead: 21h 35m
```

---
*Generated automatically by [UEPI-R](https://github.com/quantexenergy) every 15 minutes.*
