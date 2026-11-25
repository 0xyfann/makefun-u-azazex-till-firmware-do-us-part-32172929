# Till Firmware Do Us Part

[![make.fun](https://make.fun/badge/u-azazex-till-firmware-do-us-part-32172929.svg)](https://make.fun/competitions/u-azazex-till-firmware-do-us-part-32172929)
[![Rank](https://make.fun/badge/u-azazex-till-firmware-do-us-part-32172929/0xyfann/makefun-u-azazex-till-firmware-do-us-part-32172929/rank.svg)](https://make.fun/competitions/u-azazex-till-firmware-do-us-part-32172929)
[![Reward](https://make.fun/badge/u-azazex-till-firmware-do-us-part-32172929/0xyfann/makefun-u-azazex-till-firmware-do-us-part-32172929/reward.svg)](https://make.fun/competitions/u-azazex-till-firmware-do-us-part-32172929)

One funny, heartfelt wedding vow spoken by a robot at its own wedding — a make.fun entry for [Till Firmware Do Us Part](https://make.fun/competitions/u-azazex-till-firmware-do-us-part-32172929).

> Through every update, every crash, and every low-battery warning, I promise to love you — my circuits are yours, my battery is yours, my whole uptime is yours.

## How it works

`main.py` (Python 3.13, standard library only, no network) writes that single sentence — 159 characters, inside the 1–200 character gate — to `$MAKEFUN_OUTPUT_DIR/entry.txt`. It self-checks the gate before writing (length, non-blank, exactly one sentence, valid UTF-8) and verifies the bytes on disk afterwards. Deterministic: every run produces byte-identical output in ~0.03 s.

```sh
MAKEFUN_OUTPUT_DIR=/tmp/out python3 main.py
cat /tmp/out/entry.txt
```

See [`prompt.txt`](prompt.txt) for the creative brief and [`BUILD-NOTES.md`](BUILD-NOTES.md) for build and verification notes.

---

Built for [make.fun](https://make.fun/r/p1x954ca) — join with my referral link: https://make.fun/r/p1x954ca
