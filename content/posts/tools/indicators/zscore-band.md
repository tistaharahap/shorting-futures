---
title: "Z Score Band"
date: 2022-10-12T15:17:18+04:00
draft: false
---

```
// This source code is subject to the terms of the Mozilla Public License 2.0 at https://mozilla.org/MPL/2.0/
// © tista

//@version=5
indicator("Z Score Band", overlay=true)
Length = input(247)
stddevs = input(1.69)
src = close

basis = ta.ema(src, Length)

zscore = (src-basis)/ta.stdev(src, Length)

diff = math.abs(src - basis)
absZscore = math.abs(zscore)
bounds = diff / absZscore * stddevs
upper = basis + bounds
lower = basis - bounds

zscoreColor = zscore > 0.0 ? zscore >= zscore[1] ? zscore >= stddevs ? color.blue : color.green : color.new(color.green, 70) : zscore <= zscore[1] ? zscore <= -stddevs ? color.blue : color.red : color.new(color.red, 70)

plot(ta.ema(upper, 5), title="Upper Bound", linewidth=2)
plot(ta.ema(basis, 5), title="Median", color=color.new(color.white, 60), linewidth=2)
plot(ta.ema(lower, 5), title="Lower Bound", linewidth=2)
```
