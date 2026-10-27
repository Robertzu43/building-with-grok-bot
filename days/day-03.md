# Day 3 — 2026-10-27

## Summary

Tested Kronos, a viral open-source model that predicts trading candles, with Grok Bot ([@bot](https://x.com/bot)). Posted at 3:50 PM Bogotá time ([post](https://x.com/robzu99/status/2115185633522278879)); the post quotes an earlier post ([quoted post](https://x.com/robzu99/status/2115181750213312534)). Not trading advice.

## Objective

Test Kronos-mini, zero-shot and out of the box, on 8 perps for 24h direction.

## Method

- Research. Traced the original repo, its paper, and its training cutoff to avoid leakage.
- Pre-registration. Rules locked (pre-registered) before seeing any result: 8 perps, 24h direction.
- Setup. Kronos-mini zero-shot, out of the box, no extra training.
- Engine. A backtester that checks itself against raw data.
- Go/no-go gate. The calibration window (Jan-Jun 2025) must pass, or the real test never runs.

## Results

Over 6 months, Kronos-mini zero-shot returned about -49% after costs. Plain 24h momentum on the same coin-days returned about +60%.

| Item | Result |
| --- | --- |
| Kronos-mini zero-shot, after costs | -48.6% |
| Plain 24h momentum, same coin-days | +60.3% |
| Calibration gate (Jan-Jun 2025) | IC_res 0.008, t 0.19, FAILED |

## Decision

The calibration window failed, so the test window was never run. The Apr-Sep 2026 holdout stays sealed.

## Takeaways

The gate failed (IC_res 0.008, t 0.19), so the test window never ran and the Apr-Sep 2026 holdout stays sealed. Over 6 months, Kronos-mini zero-shot returned -48.6% after costs, and plain 24h momentum on the same coin-days returned +60.3%.

## Sources

- Day 3 post, 3:50 PM Bogotá time: https://x.com/robzu99/status/2115185633522278879
- Quoted post: https://x.com/robzu99/status/2115181750213312534
- Kronos: https://github.com/shiyu-coder/Kronos
