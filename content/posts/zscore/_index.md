---
title: "Z Score"
date: 2022-10-16T15:17:18+04:00
draft: false
---

## What is Zscore?

In simple terms, it's a way for us to determine outliers. A more formal explanation below.

> Z-scores are a way to compare results to a “normal” population. Results from tests or surveys have thousands of possible results and units; those results can often seem meaningless. For example, knowing that someone’s weight is 150 pounds might be good information, but if you want to compare it to the “average” person’s weight, looking at a vast table of data can be overwhelming (especially if some weights are recorded in kilograms). A z-score can tell you where that person’s weight is compared to the average population’s mean weight. [Link →](https://www.statisticshowto.com/probability-and-statistics/z-score/)

## Why Zscore?

To detect outliers and in our case, to determine if a long green candle is a pump or not. The formula for Zscore involves a moving average as its basis. For our case, we are using an Exponential Moving Average with a period of 247. If you're curious why 247 is the period, [click here!](https://angelnumber.org/247-angel-number/)

Here's a video of executing statistical arbitrage trading using Zscore.

{{< youtube aaNgZpSIm0U >}}

The term used in the video is `codependency` which I absolutely like. It's saying to us that there is a dependency between 2 completely different pairs and that the 2 pairs depend on eact other. After all market makers are robots, they move in harmony to bull trap new blood. This concept will be used later on when we start learning about indicators created for this reason. In the mean time, here's another interesting idea of using Standard Deviations to trade crude oil.

{{< youtube 9599Ixn0K38 >}}

## How Do Zscore Become Effective?

The last video talks about standard deviations larger than 1.69 and lower than -1.69 as outliers. In crypto though and especially altcoins, the threshold may be different for different coins. Sometimes you'll just see a completely abandoned coin by market makers but when it pumps, it's going shoot so high that its Zscore for the candle when the pump happened can shot above 10.

Rule of thumb:

* Parameters change all the time
* No 1 size fits all if using Zscore just for 1 pair
* If used for comparing multiple coins, 1.69 may just be enough.

## Show Me Zscore

Here you go.

![Zscore](https://s3.tradingview.com/snapshots/n/NbTwV6iV.png)

The first pump has a Zscore of `2.96` at its peak while the second one has a Zscore of `3.42` at its peak. Now let's see how many percent the market moves up and down.

![Market Moves](https://s3.tradingview.com/snapshots/o/o9ocQFa8.png)

What does this chart tells us? A few things:

* In a perfect world, when the Zscore peaked, prices will fall afterwards. Unfortunately nothing is perfect but we do get lucky once in a while.
* On the second pump, right after the Zscore peaked, it was dumped with a volume almost the same with the pump but prices didn't go down too much. New blood bought the bull trap.
* The dump after the pump **ALWAYS HAPPENS**. It's ok to miss the move up but make sure your short the move down.
* The dump lasts longer than the pump to squeeze every bit of profits from new blood.
* Spot pumps, futures dumps, **ALWAYS**. Especially in Binance where you borrow asset to do a leveraged trade in spot pairs.
* Market making's definition is actually hedging risks to be as close to 0 as possible. It has gone beyond making orders in different price levels although this is the ultimate basics.

The following is a collection of charts showing the same behavior throughout Binance's Spot &amp; Futures market.

![AXSUSDT](https://s3.tradingview.com/snapshots/t/TykQWNSF.png)

![APEUSDT](https://s3.tradingview.com/snapshots/v/viXOb2hi.png)

![RSRUSDT](https://s3.tradingview.com/snapshots/e/emiiZWkM.png)

I admit, the more examples I gave, the more inaccurate Zscore is in determining the top. That's because Zscore is not designed to detect the top, it's designed to detect outliers, that's it. Especially in the `RSRUSDT` chart, there are plenty of whiplash moves happening in the chart. **Mind your position size for cross margins and use a lower leverage for isolated margins!** We will talk about this more later.

Above said, we can see clearly there's a divergence between the tops of the prices and the tops of the Zscores. A bearish divergence to be more exact and that happened a few times in the chart but the move to go higher was stronger, the dump didn't pressure the price to its support level before the pump. This means we need to look at this at a higher timeframe.

![RSRUSDT - 1D](https://s3.tradingview.com/snapshots/h/HjXLQXor.png)

It's clear that in the 1D timeframe, `RSRUSDT`'s Zscore is under `0` since early 2022 and we also see divergences happening, bullish divergences between March to June which eventually pushes the price up in mid June. It has since been getting higher lows for its Zscores. This means this coin favors upwards moves rather than downwards moves for the last ~5.5 months.

We can still short but we do so using higher timeframes. If you're used to having your entries in 15m timeframe, try checking 4H trends first. In fact, at the minimum always check 4H trends all the time. The safe move is not to short this coin though because there are plenty other coins like `REEFUSDT` that's more favorable toward shorts.

## Can I Trade Just Using Zscore Alone?

Hell Yes!

Most of the Discord group peeps have proven it. From $2200 to $13000 and 100 trades using Zscore without a loss, it's possible. But herein lies the pickle.

Success stories comes from humility, traders trade against themselves, not the market. As we all know, the hardest part of trading is the exit part. The more you reverse engineer yourself and put your mental state in a position where you are going to be more successful then the chance of you actually being successful increases. The liquidity is there in the market, that's a fact.

There are no concepts or indicators or setups that's going to make you know yourself better. It's our psychology that's being exploited by market makers, the very nature of pump and dump is an indicator for how the market makers want you to think or worse: feel. Don't beat the market, beat yourself so you can ride the market.

---

Now, all the above said, let's get on to more interesting stuffs.

[Take Me There →]({{< relref "posts/zscore/codependency.md" >}})
