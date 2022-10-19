---
title: "MAD - Score VS Spot"
date: 2022-10-14T15:17:18+04:00
draft: false
---

## Source Code

```
//@version=5
indicator("MAD - Score Spot", format=format.price)
length = input(247)
stddevs = input(1.69)
spot = input.symbol("", "", inline="Spot Symbol")
[spOpen, spHigh, spLow, spClose] = request.security(spot, timeframe.period, [open, high, low, close], ignore_invalid_symbol=true)
spOpen := spOpen ? spOpen : na
spHigh := spHigh ? spHigh : na
spLow := spLow ? spLow : na
spClose := spClose ? spClose : na
src = (close - spClose) / close * 100
srcMedian = ta.median(src, length)

absDeviation = math.abs(src - srcMedian)
absDeviationMedian = ta.median(absDeviation, length)
mad = absDeviationMedian * 1.486

basis = ta.ema(src, length)

zscore = (src - srcMedian) / mad
zscoreColor = zscore > 0.0 ? zscore >= zscore[1] ? zscore >= stddevs ? color.blue : color.green : color.new(color.green, 70) : zscore <= zscore[1] ? zscore <= -stddevs ? color.blue : color.red : color.new(color.red, 70)

plot(zscore, title="Z Score", color=zscoreColor, style=plot.style_histogram, linewidth=2)

hline(stddevs, color=color.new(color.white, 90), linestyle=hline.style_dashed)
hline(-stddevs, color=color.new(color.white, 90), linestyle=hline.style_dashed)
hline(0.0, color=color.new(color.white, 90), linewidth=2, linestyle=hline.style_solid)

```
