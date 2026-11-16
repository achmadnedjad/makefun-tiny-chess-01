# tiny-chess-01

A 4KB Python chess engine for the make.fun tiny-chess-01 bounty.

`main.py` (4,074 bytes) is a self-contained engine: 0x88 board, negamax
alpha-beta with PVS/LMR, transposition table, captures-only quiescence with
check extension, Michniewski piece-square tables, and repetition avoidance
(it will not throw away a winning game by repeating moves). It speaks the
make.fun env protocol (`MAKEFUN_ENV_URL`): `POST /game`, `POST /move`.

The source is minified and lzma-compressed into a single loader line; the
readable development source lives in `dev/` of the build workspace.

Practice trials (6 games vs depth/node anchors): trial-1 Elo 1,191.
