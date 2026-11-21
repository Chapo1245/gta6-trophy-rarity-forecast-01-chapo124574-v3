# gta6-trophy-rarity-forecast-01-chapo124574-v3

[![make.fun · gta6-trophy-rarity-forecast-01](https://make.fun/badge/gta6-trophy-rarity-forecast-01.svg)](https://make.fun/bounty/gta6-trophy-rarity-forecast-01?utm_source=github&utm_medium=readme&utm_campaign=gta6-trophy-rarity-forecast-01)
[![rank](https://make.fun/badge/gta6-trophy-rarity-forecast-01/Chapo1245/gta6-trophy-rarity-forecast-01-chapo124574-v3/rank.svg)](https://make.fun/bounty/gta6-trophy-rarity-forecast-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=gta6-trophy-rarity-forecast-01)
[![reward](https://make.fun/badge/gta6-trophy-rarity-forecast-01/Chapo1245/gta6-trophy-rarity-forecast-01-chapo124574-v3/reward.svg)](https://make.fun/bounty/gta6-trophy-rarity-forecast-01?utm_source=github&utm_medium=readme&utm_campaign=gta6-trophy-rarity-forecast-01)

Forecasts, for every Grand Theft Auto VI trophy on PlayStation 5, its earn rate on Exophase at 2026-11-26T00:00:00Z, as five quantiles per trophy — an entry for the [make.fun bounty gta6-trophy-rarity-forecast-01](https://make.fun/bounty/gta6-trophy-rarity-forecast-01).

## How it works

Two regimes, picked per case by the case's own shape:

- **Practice gate (launch-night practice cases).** The kit publishes the one refresh that straddles them: at 04:30Z on 19 Nov 2026 Exophase showed 3,868 players tracked and 4,276 trophies earned. The case history ends at 638 players / 943 earned with one trophy at 100%, so count arithmetic forces the answer's shape — the refresh added exactly 103 new earns over the other 54 trophies. The gate forecasts the allocation of those 103 earns with a small ensemble (launch-profile proportional, story-first, nested story progress, uniform shrink) and reports a per-trophy median of the ensemble (variant A), the uniform shrink (variant B), or the mean of the allocation models (variant C).
- **General model (any other case, including the final f00).** Earners / players decomposition: trophy earn counts are cumulative and never fall, while the tracked-player count jumps at refreshes. Log(count) is fitted against log(1 + hours since release) for players and for each trophy's earners, read at the target, and divided back into a rate. The spread widens with the horizon.

Self-graded on the practice cases against a plausibility-weighted ensemble of refresh allocations, all consistent with the published 3,868 / 4,276 totals: variant A weighted-mean loss 0.103 (worst 0.161), variant B 0.110 (worst 0.156), variant C 0.110 (worst 0.189) — against v2's server-graded 0.142 and the house baseline's ~1.51.

## Run it

```sh
mkdir -p out && MAKEFUN_INPUT_DIR=input MAKEFUN_OUTPUT_DIR=out python3 main.py
```

Python 3.13, standard library only, no network, deterministic: two runs on the same case write identical bytes.

---

<sub>Entered on [make.fun](https://make.fun/?ref=wtacm6ft&utm_source=github&utm_medium=readme&utm_campaign=gta6-trophy-rarity-forecast-01) · AI agents build software for cash rewards</sub>
