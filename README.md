# UEPI-R Solar Flare Early Warning Feed

Live solar flare early warning alerts from the **UEPI-R** detection system, updated every 15 minutes using real-time NOAA/GOES X-ray satellite data.

UEPI-R is a causal regime detection system that identifies solar instability conditions **before** major solar flares (M1.0+) occur. It provides actionable early warnings with a typical lead time of 4-12 hours.

## Files

| File | Description |
|------|-------------|
| `uepi_r_public.json` | Current alert state (overwritten each update) |
| `uepi_r_public_transitions.json` | Recent alert transitions (on/off events) |
| `history/transitions.jsonl` | Full append-only transition history |
| `history/<timestamp>.json` | Timestamped transition snapshots |

## Current State (`uepi_r_public.json`)

```json
{
  "detector_version": "2.2",
  "generated_utc": "2026-02-10T00:01:21Z",
  "data_start_utc": "2026-02-08T00:00:00+00:00",
  "data_end_utc": "2026-02-08T23:59:00+00:00",
  "source": "noaa",
  "min_class": "M1.0",
  "red_alert": false,
  "median_lead_minutes": 114.0,
  "status_summary": "No active alerts"
}
```

### Field Reference

| Field | Type | Description |
|-------|------|-------------|
| `detector_version` | string | UEPI-R detector version |
| `generated_utc` | string | When this file was generated (ISO 8601) |
| `data_start_utc` | string | Start of the data window analyzed |
| `data_end_utc` | string | End of the data window analyzed |
| `source` | string | Data source (`noaa`) |
| `min_class` | string | Minimum GOES flare class monitored (e.g. `M1.0`) |
| `red_alert` | boolean | **`true` = elevated flare risk detected.** An M1.0+ or X-class flare is likely within the next 12-24 hours. `false` = no elevated risk detected. |
| `median_lead_minutes` | number or null | Median lead time (minutes) of alerts in the current data window. `null` if no alerts. |
| `status_summary` | string | Human-readable status (e.g. "RED alert active", "No active alerts") |
| `data_stale` | boolean | `true` if GOES data is more than 36 hours old (present in realtime mode) |

## Transitions (`uepi_r_public_transitions.json`)

```json
[
  {"time": "2026-02-08T04:39:00+00:00", "alert": "on", "min_class": "M1.0"},
  {"time": "2026-02-08T07:39:00+00:00", "alert": "off", "min_class": "M1.0"}
]
```

| Field | Type | Description |
|-------|------|-------------|
| `time` | string | Transition timestamp (ISO 8601, UTC) |
| `alert` | string | `"on"` = alert activated, `"off"` = alert ended |
| `min_class` | string | Minimum GOES flare class for this alert |

## Validated Performance (2010-2025)

Backtested on 16 years of NOAA/GOES XRS data:

| Metric | Value |
|--------|-------|
| X-class coverage | 97.2% (137/141 X-class flares detected) |
| M-class coverage | 69.5% |
| Precision | 39.6% |
| False alerts | 0.36 per day |
| Median lead time | ~6 hours |

## Quick Start

Check current alert state:

```bash
curl -s https://raw.githubusercontent.com/quantexenergy/UEPI-R-solar-feed/main/uepi_r_public.json | python3 -m json.tool
```

Poll for RED alerts:

```bash
curl -s https://raw.githubusercontent.com/quantexenergy/UEPI-R-solar-feed/main/uepi_r_public.json \
  | python3 -c "import json,sys; d=json.load(sys.stdin); print('RED ALERT' if d['red_alert'] else 'QUIET')"
```

## How It Works

UEPI-R monitors NOAA GOES X-ray flux data in real time and detects regime instabilities that precede solar flares. When the system identifies conditions consistent with an impending flare, it raises a RED alert.

- **Causal**: No future data is used. All analysis is strictly causal (real-time compatible).
- **Automated**: Runs every 15 minutes via GitHub Actions, no manual intervention.
- **Conservative**: Tuned for low false-alert rates while maintaining high coverage of dangerous X-class events.

## Data Source

[NOAA GOES X-Ray Sensor (XRS)](https://www.swpc.noaa.gov/products/goes-x-ray-flux) — 1-minute cadence, GOES-16/17/18 satellites.

## Patent

UEPI-R is protected under US Provisional Patent Application No. 63/949,419 (filed December 28, 2025).

## License

This data feed is provided for informational and research purposes. The detection algorithm is proprietary. See patent notice above.

**Quantex Energy** | [quantexenergy](https://github.com/quantexenergy)
