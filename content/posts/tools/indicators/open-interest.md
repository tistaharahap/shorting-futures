---
title: "Open Interest in USDT"
date: 2022-10-13T15:17:18+04:00
draft: false
---

## Source Code

```
//@version=5
indicator("Open Interest + Volume", "OIV", format = format.volume)

bool overwriteSymbolInput = input.bool(false, "Override symbol", inline = "Override symbol")
string tickerInput = input.symbol("", "", inline = "Override symbol")
int oiEmaPeriod = input.int(247, "OI EMA Period")

string symbolOnly = str.substring(tickerInput, str.pos(tickerInput, ":") + 1)
string userSymbol = overwriteSymbolInput ? symbolOnly : syminfo.prefix + ":" + syminfo.ticker
string openInterestTicker = str.format("{0}_OI", userSymbol)
string timeframe = syminfo.type == "futures" and timeframe.isintraday ? "1D" : timeframe.period
[oiOpen, oiHigh, oiLow, oiClose, oiColorCond] = request.security(openInterestTicker, timeframe, [open, high, low, close, close > close[1]], ignore_invalid_symbol = true)
oiOpen := oiOpen ? oiOpen * close : na
oiHigh := oiHigh ? oiHigh * close : na
oiLow := oiLow ? oiLow * close : na
oiClose := oiClose ? oiClose * close : na

oiCloseEma = ta.ema(oiClose, oiEmaPeriod)

hasOHLC = ta.cum(oiOpen)
straightFiveGreens = oiColorCond and oiColorCond[1] and oiColorCond[2] and oiColorCond[3] and oiColorCond[4]
straightFiveReds = not oiColorCond and not oiColorCond[1] and not oiColorCond[2] and not oiColorCond[3] and not oiColorCond[4]
markedCandle = straightFiveGreens or straightFiveReds
color openInterestColor = oiColorCond ? color.teal : color.red
plot(hasOHLC ? na : oiClose, "Futures Open Interest", openInterestColor, style = plot.style_stepline)
plot(oiCloseEma, title="OI EMA", color=color.blue)
plotcandle(oiOpen, oiHigh, oiLow, hasOHLC ? oiClose : na, "Crypto Open Interest", color = openInterestColor, wickcolor = openInterestColor, bordercolor = openInterestColor)

oiRatio = oiClose / oiCloseEma - 1
oiRatioThreshold = input.float(10.0, title="OI Ratio Threshold %")

// AO
aoEmaPeriod = input(8, title="AO EMA Period")

ao = ta.sma(hl2, 5) - ta.sma(hl2, 34)
emaAo = ta.ema(ao, aoEmaPeriod)
aoCrossUp = ta.crossover(ao, emaAo)
aoCrossDown = ta.crossunder(ao, emaAo)

// Candle Action
actionPeriod = input.int(3, title="Candle Action Lookback Period")
actionPercentage = input.float(3.0, title="Candle Action Percentage Threshold")

// Short
// pumpLookbackPeriod = input.int(8, title="Pump Lookback Period")
// hasPumped = oiRatio > oiRatioThreshold / 100.0 and ((close / close[actionPeriod] - 1.0) * 100.0 >= actionPercentage)
// pumpIsAlive(lookback) =>
//     for i = 1 to lookback
//         if hasPumped[i]
//             true

// shortNow = pumpIsAlive(pumpLookbackPeriod) and aoCrossDown
// barcolor(shortNow ? color.yellow : na)
// bgcolor(shortNow ? color.new(color.red, 50) : na)
```
