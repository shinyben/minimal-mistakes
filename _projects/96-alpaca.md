---
title: "Algorithmic Trading"
excerpt: "Built, tested, and ran an algorithmic trading setup using Quantopian and Alpaca."
header:
  teaser: /assets/img/projects/alpaca/backtest.PNG
gallery:
  - url: /assets/img/projects/alpaca/alpaca.PNG
    image_path: /assets/img/projects/alpaca/alpaca.PNG
    alt: "alpaca"
---

During Spring 2019, I started to get interested in trading stocks and the mechanics surrounding doing so. I started manually trading with [Robinhood](https://robinhood.com/), but quickly realized that if I wanted to capitalize on weekly changes, I would have to put in a lot of time doing simple and repetitive tasks. Since my internship during Summer 2019 dealt with automation, I felt that this was a perfect testing bed to see if I could apply what I had learned.

I started from Quantopian, an algorithmic trading site and community, familiarizing myself with the platform and pipeline. After looking at a few example algorithms, like [Sample Mean Reversion](https://medium.com/auquan/mean-reversion-simple-trading-strategies-part-1-a18a87c1196a), I explored the community to see what the current best practices were.

After obtaining an algorithm I was confident enough to run live, I migrated the code from Quantopian to pylivetrader's framework. Then I got set up in [Alpaca](https://alpaca.markets/), a stock trading API which would allow me to set my algorithm to work on real money. As of the time of this blogpost's writing, the algorithm has achieved a 10% return.

{% include gallery caption="An example day using the algorithm for live trading." %}

Initially, I ran the code from my home computer. Because it has to be running during regular trading hours, though, I plan to migrate the code to run on Google Cloud Platform VM.
