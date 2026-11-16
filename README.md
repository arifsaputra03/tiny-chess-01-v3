# tiny-chess-01 v3

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/arifsaputra03/tiny-chess-01-v3/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/arifsaputra03/tiny-chess-01-v3/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A 4 KB Python chess engine for the [make.fun tiny-chess-01 bounty](https://make.fun/bounty/tiny-chess-01): 0x88 board, alpha-beta + PVS, null-move pruning, quiescence search, history/killer moves, Zobrist hashing, 120,000 nodes per move. v3 of the entry — v2 "Neutral Echo" scored server dev Elo 1364.

## How it plays

A make.fun harness client, not a standalone UI: it reads the trial brief and plays 8 games against the house gauntlet through the env at `MAKEFUN_ENV_URL`, then exits. No model calls — a scripted program is a legal entry here.

## Run it locally

Grade it the way the server does (kit + Docker):

    node cli/makefun.mjs grade-local --kit . --bot <repo> --driver docker --instances 3

## Results (practice trials, 120k nodes)

| version | t0 | t1 | t2 | avg |
| --- | --- | --- | --- | --- |
| v3 | 1545 | 1545 | 2112 | 1734 |
| v2 | 1364 | 1364 | 2112 | 1613 |

v3c rewrote the engine (397 of 510 source lines differ from v2) with identical behavior — perft/eval/bench exact (kiwipete 48). Server dev score for v3 is pending.

## Files

- `main.py` (4,066 bytes) — the entrypoint, packed from readable `src.py` with the kit's `makefun compress`. `src.py` stays out of the tree so the repo fits the 8,192-byte cap.
- `LICENSE` — MIT.

[Play the bounty on make.fun](https://make.fun/bounty/tiny-chess-01). Optional: earn referral rewards — [join make.fun with my referral link](https://make.fun/r/yny5gqnv).
