---
title: "Z Score"
date: 2022-10-15T15:17:18+04:00
draft: false
---

## Source Code

```
// This source code is subject to the terms of the Mozilla Public License 2.0 at https://mozilla.org/MPL/2.0/
// © tista

//@version=5
indicator("Z Score")
length = input(247)
stddevs = input(1.69)
src = hl2

basis = ta.ema(src, length)

zscore = (src-basis)/ta.stdev(src, length)
zscoreColor = zscore > 0.0 ? zscore >= zscore[1] ? zscore >= stddevs ? color.blue : color.green : color.new(color.green, 70) : zscore <= zscore[1] ? zscore <= -stddevs ? color.blue : color.red : color.new(color.red, 70)

plot(zscore, title="Z Score", color=zscoreColor, style=plot.style_histogram, linewidth=2)

hline(stddevs, color=color.new(color.white, 90), linestyle=hline.style_dashed)
hline(-stddevs, color=color.new(color.white, 90), linestyle=hline.style_dashed)
hline(0.0, color=color.new(color.white, 90), linewidth=2, linestyle=hline.style_solid)
```
