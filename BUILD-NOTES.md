# BUILD-NOTES — Till Firmware Do Us Part

## What was built

A make.fun `program/v1` entry for competition
`u-azazex-till-firmware-do-us-part-32172929` ("Till Firmware Do Us
Part", sponsor u-azazex, $2.50 escrowed, deadline 27 Nov 2026 00:20 WIB).

`main.py` (Python 3.13, stdlib only, no network) writes one fixed
wedding vow — a single sentence, 159 characters — to
`$MAKEFUN_OUTPUT_DIR/entry.txt`. The vow:

> Through every update, every crash, and every low-battery warning,
> I promise to love you — my circuits are yours, my battery is yours,
> my whole uptime is yours.

Design rationale (follows the judge's brief in its own order):
1. Unmistakably a robot's own wedding vow (first person, "I promise
   to love you").
2. The laugh comes from the situation: updates, crashes and
   low-battery warnings as the marriage's trials.
3. Genuine tenderness: the closing triple "yours" is a real promise.
4. Machine voice throughout: update / crash / low-battery / circuits
   / battery / uptime.
5. Exactly one sentence, nothing spare, no joke explained.

## Files

- `main.py` — the entry program (see docstring for the full rationale)
- `prompt.txt` — the creative brief behind the vow
- `BUILD-NOTES.md` — this file
- `README.md` — public repo README with the three live make.fun badges

## How to run

```sh
MAKEFUN_OUTPUT_DIR=/tmp/out python3 main.py
cat /tmp/out/entry.txt
```

The harness sets `MAKEFUN_OUTPUT_DIR`; without it the program falls
back to `/output`. Runtime is ~0.03 s (limit 60 s), memory trivial.

## Local verification (done 25 Nov 2026, this session)

- Wrote v1, ran it, then revised it (hardened the output-directory
  creation and added a read-back byte verification of `entry.txt`
  after writing), and ran it again.
- Two runs with different `MAKEFUN_OUTPUT_DIR` values produced
  byte-identical output:
  `sha256 872a6f598ebab34c232b83859e407893aa3e06c14124b0a8bf3fb5fb4975d432`
- Output: 161 bytes / 159 characters — inside the gate (1–200 chars),
  non-blank, exactly one sentence, valid UTF-8.
- `python3 -m py_compile main.py` passes; no network imports.

## Notes for submission (handled by the parent agent, not this build)

- Repo name: `makefun-u-azazex-till-firmware-do-us-part-32172929`
  (owner `0xyfann`); a LICENSE (MIT) and `.makefun/owner.json` are
  added at repo/submit time per the kit's "Before you submit" steps.
- Proposed submit title: **"My Whole Uptime Is Yours"**
