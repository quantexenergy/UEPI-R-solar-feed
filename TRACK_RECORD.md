# UEPI-R Track Record

Automated verification of UEPI-R alerts against [NOAA's official flare event list](https://services.swpc.noaa.gov/json/goes/primary/xray-flares-7-day.json).
Each alert is verified 24 hours after it fires. Git commit history proves every alert was published **before** the flare occurred.

## Summary

| Metric | Value |
|--------|-------|
| Verified hits | **29** |
| M-class coverage | **66.7%** (28/42 flares) |
| M-class hit rate | **29.2%** (28/96) |
| X-class hit rate | **1.0%** (1/96) |
| False alerts | 67/96 |
| C-class associated | 57/67 false alerts |
| Median lead time | **10h 37m** |
| Pending verification | 1 |
| Last updated | 2026-05-02T02:00:30Z |

A baseline-window bug inflated false alerts before March 21, 2026.
The **Since Fix** column reflects corrected performance.

| Metric | Lifetime | Since Fix (Mar 21) |
|--------|:--------:|:------------------:|
| M-class coverage | 66.7% (28/42) | **66.7%** (20/30) |
| X-class hits | 1 | **1** |
| Precision | 30.2% | **52.5%** |
| False alerts | 67 | **19** |
| Median lead time | 10h 37m | **10h 53m** |
| Alerts | 96 | 40 |

## Event Log

```diff
! C-ASSOCIATED Alert: 2026-04-30 09:15 UTC  |  No M1.0+ (C3.7 at 09:35)
! C-ASSOCIATED Alert: 2026-04-30 00:45 UTC  |  No M1.0+ (C3.7 at 09:35)
! C-ASSOCIATED Alert: 2026-04-29 05:00 UTC  |  No M1.0+ (C5.1 at 00:24)
! C-ASSOCIATED Alert: 2026-04-28 18:45 UTC  |  No M1.0+ (C5.1 at 04:39)
! MISS Flare: M1.1 at 2026-04-28 14:03 UTC  |  No alert issued
+ HIT  Alert: 2026-04-28 08:30 UTC  |  Flare: M1.5 at 2026-04-28 13:49 UTC  |  Lead: 5h 18m
+ HIT  Alert: 2026-04-27 23:30 UTC  |  Flare: M1.0 at 2026-04-28 12:17 UTC  |  Lead: 12h 46m
! C-ASSOCIATED Alert: 2026-04-27 07:00 UTC  |  No M1.0+ (C5.4 at 07:38)
! MISS Flare: M1.0 at 2026-04-27 06:39 UTC  |  No alert issued
+ HIT  Alert: 2026-04-26 11:30 UTC  |  Flare: M6.0 at 2026-04-26 22:51 UTC  |  Lead: 11h 20m
+ HIT  Alert: 2026-04-26 07:30 UTC  |  Flare: M2.2 at 2026-04-26 19:54 UTC  |  Lead: 12h 23m
+ HIT  Alert: 2026-04-26 00:30 UTC  |  Flare: M1.7 at 2026-04-26 19:18 UTC  |  Lead: 18h 47m
+ HIT  Alert: 2026-04-25 19:45 UTC  |  Flare: M1.4 at 2026-04-26 13:54 UTC  |  Lead: 18h 08m
+ HIT  Alert: 2026-04-25 13:30 UTC  |  Flare: M1.3 at 2026-04-26 00:08 UTC  |  Lead: 10h 37m
+ HIT  Alert: 2026-04-25 08:15 UTC  |  Flare: M1.1 at 2026-04-25 14:22 UTC  |  Lead: 6h 06m
! MISS Flare: M1.3 at 2026-04-25 07:56 UTC  |  No alert issued
+ HIT  Alert: 2026-04-24 17:30 UTC  |  Flare: M6.4 at 2026-04-24 17:54 UTC  |  Lead: 23min
! MISS Flare: M1.7 at 2026-04-24 12:34 UTC  |  No alert issued
+ HIT  Alert: 2026-04-24 08:15 UTC  |  Flare: M1.9 at 2026-04-24 08:57 UTC  |  Lead: 42min
! MISS Flare: X2.5 at 2026-04-24 08:01 UTC  |  No alert issued
+ HIT  Alert: 2026-04-23 23:30 UTC  |  Flare: X2.4 at 2026-04-24 00:51 UTC  |  Lead: 1h 20m
+ HIT  Alert: 2026-04-23 14:00 UTC  |  Flare: M4.9 at 2026-04-23 17:00 UTC  |  Lead: 2h 59m
! MISS Flare: M1.7 at 2026-04-23 13:42 UTC  |  No alert issued
! MISS Flare: M4.3 at 2026-04-23 08:40 UTC  |  No alert issued
+ HIT  Alert: 2026-04-22 23:30 UTC  |  Flare: M1.2 at 2026-04-23 04:50 UTC  |  Lead: 5h 19m
+ HIT  Alert: 2026-04-22 17:30 UTC  |  Flare: M1.6 at 2026-04-23 04:24 UTC  |  Lead: 10h 53m
! C-ASSOCIATED Alert: 2026-04-21 12:01 UTC  |  No M1.0+ (C1.9 at 14:15)
! C-ASSOCIATED Alert: 2026-04-21 06:15 UTC  |  No M1.0+ (C4.0 at 11:45)
- FALSE Alert: 2026-04-17 04:45 UTC  |  No M1.0+ flare within 24h
- FALSE Alert: 2026-04-09 08:45 UTC  |  No M1.0+ flare within 24h
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
*Generated automatically by [UEPI-R](https://github.com/quantexenergy) every 15 minutes.*
