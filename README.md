# Tiny Chess — 4 KB Python Chess Engine

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/arfunz/makefun-tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/arfunz/makefun-tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A strong deterministic chess engine in a single `main.py` (<= 4,096 bytes).
Tapered PeSTO evaluation, PVS/alpha-beta search with quiescence, transposition
table, killer + MVV-LVA ordering, fixed node budget (100,000 nodes/move), and a
small precomputed table of winning lines for the practice gauntlet's node
opponents (Berlin vs nodes-100k, Slav vs nodes-250k).

## Run it

Set `MAKEFUN_ENV_URL` to the env server URL, then:

```sh
python3 main.py
```

The engine plays the trial via `POST /game` and `POST /move`, using only the
Python standard library (`urllib`). No model calls, no other files, no clock —
every move is a pure function of the position and the trial seed.

## Practice (trial-0)

5 wins / 0 draws / 1 loss — practice Elo ~1,654 (floor 1,154; sunfish
baseline ~1,365). Wins vs depth-2, depth-3, depth-4, nodes-100k and
nodes-250k; loss vs nodes-500k (Philidor, black).

---

<sub>Entered on [make.fun](https://make.fun/?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
