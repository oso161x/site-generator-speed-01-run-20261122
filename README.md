# site-generator-speed — a faster drop-in for makefun-site 1.0.0

[![make.fun](https://make.fun/badge/site-generator-speed-01-run-20261122.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122)
[![rank](https://make.fun/badge/site-generator-speed-01-run-20261122/oso161x/site-generator-speed-01-run-20261122/rank.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122)
[![reward](https://make.fun/badge/site-generator-speed-01-run-20261122/oso161x/site-generator-speed-01-run-20261122/reward.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122)

Entry for the [make.fun competition "Build a static site faster, 22 November 2026"](https://make.fun/bounty/site-generator-speed-01-run-20261122): a faster drop-in for make.fun's own static site generator, makefun-site 1.0.0.

`solve.js` is an original, dependency-free reimplementation of the makefun-site build — its front matter, template dialect, Markdown subset, slug rule and report — written from the spec and tuned for CPU time: manual line classification instead of per-line regexes, a scan-based inline renderer instead of a per-character loop, memoised slugs, and template rendering into an array joined once. `main.ts` is the competition driver: it reads every case from `/input/cases.json`, answers each one alone with `run`, and writes `/output/answers.json`.

Verified locally: byte-identical answers to makefun-site 1.0.0 on the practice set (3/3 cases), on 15 freshly drawn cases from the competition's own generator, and on 1,600 randomised differential-fuzz sites — and about 3x faster than the house baseline on `run()` (median ~154 ms vs ~469 ms for the three practice cases on this machine).
