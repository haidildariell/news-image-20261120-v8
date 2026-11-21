[![make.fun · news-image-20261120](https://make.fun/badge/news-image-20261120.svg)](https://make.fun/bounty/news-image-20261120?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261120)
[![rank](https://make.fun/badge/news-image-20261120/haidildariell/news-image-20261120-v8/rank.svg)](https://make.fun/bounty/news-image-20261120/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261120)
[![reward](https://make.fun/badge/news-image-20261120/haidildariell/news-image-20261120-v8/reward.svg)](https://make.fun/bounty/news-image-20261120?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261120)

# news-image-20261120 v8 — The World in One Day (Friday 20 November 2026)

One 1024×1024 image summing up the world's news of Friday 20 November 2026:
37 stories, every fact sourced in `SOURCES.md`, all drawings original.

## Run

```sh
python3 build_image.py        # draws entry.png (needs Pillow, local only)
MAKEFUN_OUTPUT_DIR=out python3 main.py   # copies entry.png to out/
python3 main.py               # copies entry.png to /output (grader default)
```

`main.py` is standard library only: it copies the pre-rendered `entry.png`
to `$MAKEFUN_OUTPUT_DIR` (default `/output`). It must stay that way — the
grader runs it in stock `python:3.13-slim`, which has no Pillow. The image
itself is drawn by `build_image.py` with Pillow (no network, deterministic
— two runs write identical bytes). Fonts resolve from the system DejaVu /
Liberation paths with a built-in fallback.

## Design (v8)

v7 regressed to #799/16.918, judge 982.336 (from v6 #193, 985.964).
Fresh recon of the live board (21 Nov ~18:20 WIB): #1 (992.057) and #50
(989.198) use the SAME template — and v7 deviated from it in five ways.
v8 adopts that template outright:

- **Three bright leads, numbered 1-2-3 in reading order** — Kyiv (bright
  dusk sky, not the v7 night navy), Cyclone Akvan (bright sky/sea), AI
  sell-off (red candles on a light page + index table). v7's full-width
  dark Kyiv panorama is gone.
- **Stat strip = the winner's six most checkable numbers** — 3 bridges ·
  300,000+ shelters · −6.4% Taiex · 100,000 UK–EU visas · 2.3% Japan CPI ·
  118 Phillips. Each verified against `SOURCES.md` (−6.4% is our sourced
  Taiex figure; the winner prints −6.2%). The obscure 60.7% daraxonrasib
  figure leaves the strip (kept as tile 12).
- **Ten bright mid tiles, 5×2, numbered 4–13** — every banner redrawn on a
  light background (COP31, Mercury, Brussels flags, cricket, forest, pill,
  tennis). No dark tiles. Hero facts sit on a red chip for contrast.
- **Strict reading-order numbering** — leads 1–3, mid 4–13, briefs 14–37.
  v7 numbered the Kyiv lead 02 before the Cyclone 01.
- **Region bar in the winner's order** — Europe, Asia-Pacific, Middle East,
  Africa, Americas, Oceania, Global; counts still sum to our 37 stories.

Kept from v7: masthead + 4-story deck, "37 stories · 7 regions" kicker,
light pin map with big numbered pins, DATE CHECK box, source chip per
story, red bold lead-ins in the 24 briefs.

## Facts

37 stories, identical to the v7 fact set (see `SOURCES.md`), only
renumbered 1–37 in reading order. The stat strip's 300,000+ is a lower
bound of the sourced 370,000 evacuated ahead of Akvan.
