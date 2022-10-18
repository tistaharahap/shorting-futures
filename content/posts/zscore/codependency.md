---
title: "Codependency"
date: 2022-10-16T15:17:18+04:00
draft: false
---

In this part, we're going to learn about market moves by analyzing another coin by using Zscore. Before that, let's talk about a feature in TradingView I discussed earlier which is to compare prices between 2 different markets of the same altcoin. Again, let's start with `REEFUSDT`.

## Comparing Candles

Let's add a price comparison in TradingView.

{{< vimeo 761318116 >}}

Now that we know how to do this, let's take things 1 level up and focus on just the delta in percentages of spot vs futures pair.

{{< vimeo 761416330 >}}

Here's a screenshot of the last chart in the video.

![Spot vs Futures Diffs](https://s3.tradingview.com/snapshots/p/pSGx15yw.png)

The formula for us to do the deltas is below:

```
(BINANCE:{FUTURES_PAIR} - BINANCE:{SPOT_PAIR}) / BINANCE:{FUTURES_PAIR} * 100
```

In this chart we have proven that there is a codependency between the same pair traded in different markets. Volatile moves are represented well in the deltas. What does that look like? You guessed it, looks like there are only a few of these volatile moves and the deltas after the volatile move is rather mundane. Z Score will be super effective? Let's have a look.

![Effective?](https://s3.tradingview.com/snapshots/8/8eDKCS0R.png)

It's now impressively clear that `REEFUSDT` wants to go up and up, we can see Z Scores painted in blue popping up numerous times. That in itself resulted a massive pump in the form of the last pump candle with the size trumping the pumps preceeding it. When do we short right?

Just looking at this chart does not inform us fully to guide us to make better decisions. As with any trade, we need to have a look at support and resistance levels, always. Let's use an indicator to look at imbalances that happened because of wicks. Link to the indicator below:

[OFIF Indicator →](https://www.tradingview.com/script/kEPvBsWe-Order-Flow-Imbalance-Finder-By-Turk/)

Let's see how it looks like on our chart.

![Order Imbalances](https://s3.tradingview.com/snapshots/v/vMD36CcS.png)

The first pump created a huge imbalance zone which I suspect in the future will become support. However, that pump only broke 1 imbalance zone but as a result of breaking that imbalance, it broke several other imbalances. Let's see how the same chart looks like with the spot candles overlaid.

![Spot overlaid](https://s3.tradingview.com/snapshots/j/JgesH5kr.png)

It's clear that the spot market went upwards by a significant percentage over the futures candle. Why? The market makers who already bought bottom hedged their holdings in the futures market creating an impenetrable sell wall. Have the market makers exited their spot holdings? I believe so, they exited so that they can create fake outs in the futures market for them to finally capitulate their futures position which is seen when the big red candle happened between hour 12-13. After that red candle, there were no buyers, price almost fell to the huge imbalance zone.

Why didn't the price fell to the imbalance zone? Simple answer, it found support in the form of a short squeeze that went unchecked because there were apparently no sellers. Proven by the lack of imbalances, the move up is started by the short squeeze but held up by an unknown force. This unknown force needs to be known!

Still, the question of when to short is not answered. Let's try to answer in the next section.

[To the next section; The Invisible Hand →]({{< relref "posts/zscore/the-invisible-hand.md" >}})
