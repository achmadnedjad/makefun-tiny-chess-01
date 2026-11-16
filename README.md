# makefun-tiny-chess-01

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/achmadnedjad/makefun-tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/achmadnedjad/makefun-tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A 4 KB Python chess engine: 0x88 board, negamax alpha-beta with PVS/LMR, transposition table, quiescence with check extension, and repetition avoidance. Practice trial-1 Elo 1,191.

## Run it

```sh
MAKEFUN_ENV_URL=http://127.0.0.1:18080 python3 main.py
```

---

<sub>Entered on [make.fun](https://make.fun/?ref=8nnd7jxs&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>

## Engine

`main.py` (4,016 bytes) is a self-contained engine: 0x88 board, negamax
alpha-beta with PVS/LMR, transposition table, captures-only quiescence with
check extension, Michniewski piece-square tables, and repetition avoidance
(it will not throw away a winning game by repeating moves). It speaks the
make.fun env protocol (`MAKEFUN_ENV_URL`): `POST /game`, `POST /move`.

`main.py` is the kit's `makefun compress` output of the readable source
`main_src.py` (kept beside it in the build workspace, not committed here):
the same engine, packed with the makefun-compress/v1 stub around an LZMA
stream. The readable source is the golfed engine (v12): minified names,
piece-square tables encoded as a letter string, PVS/LMR, transposition
table, repetition avoidance.

Practice trials (6 games vs depth/node anchors): trial-1 Elo 1,191
(2 wins, 1 draw, 3 losses — beat depth-2 as Black and depth-3 as White),
above the 1,154 practice floor.
