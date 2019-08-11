---
layout: posts
title: "Humans vs. AI, Summarized"
date: 2019-04-13
---

One way researchers have measured AI's progress has been pitting AI against humans in games. Here I'll be listing the important occurrences along that timeline.

1997 - IBM's Deep Blue defeats Gary Kasparov, the reigning chess world champion at the time.

<img src="/assets/img/posts/2019-04-13-Human-AI-Competition/Kasparov-DeepBlue.jpg" alt="Kasparov and Deep Blue">

Deep Blue worked via the [alpha-beta search algorithm](https://en.wikipedia.org/wiki/Alpha%E2%80%93beta_pruning), an example of brute force and GOFAI (Good Old-Fashioned AI).
Depending on who you ask, this may not be AI at all, although this may be due to the phenomenon that widely used methods become labeled "Not AI" after a few years of use.

2011 - IBM's Watson defeats the reigning Jeopardy! champions Rutter and Jennings.

<img src="/assets/img/posts/2019-04-13-Human-AI-Competition/Jeopardy-Watson.jpg" alt="Watson">

Watson is much more complicated, utilizing "encyclopedias, dictionaries, thesauri, newswire articles, literary works, and so on"  to supply its NLP (Natural Language Processing) language analysis algorithms, which run in parallel <sup>[[1](http://www.aaai.org/Magazine/Watson/watson.php)]</sup>. Watson's capacity to run these algorithms in parallel (more than 100 at a time!) is its main achievement <sup>[[2](https://www.nytimes.com/2010/06/20/magazine/20Computer-t.html)]</sup>.

An overview of how some of these algorithms work:
"The great shift in artificial intelligence began in the last 10 years, when computer scientists began using statistics to analyze huge piles of documents, like books and news stories. They wrote algorithms that could take any subject and automatically learn what types of words are, statistically speaking, most (and least) associated with it. Using this method, you could put hundreds of articles and books and movie reviews discussing Sherlock Holmes into the computer, and it would calculate that the words “deerstalker hat” and “Professor Moriarty” and “opium” are frequently correlated with one another, but not with, say, the Super Bowl. So at that point you could present the computer with a question that didn’t mention Sherlock Holmes by name, but if the machine detected certain associated words, it could conclude that Holmes was the probable subject — and it could also identify hundreds of other concepts and words that weren’t present but that were likely to be related to Holmes, like “Baker Street” and “chemistry.” <sup>[[2](https://www.nytimes.com/2010/06/20/magazine/20Computer-t.html)]</sup>"

2015 - DeepMind's AlphaGo defeats Fan Hui, a Go professional, 5-0.

<img src="/assets/img/posts/2019-04-13-Human-AI-Competition/Hui-Alphago.png" alt="Fan Hui and Alphago">

From what I understand, AlphaGo receives an input feature (the following picture) and uses a Deep Learning classifier to estimate the probability of the next move over all possible moves, selecting the most probable.

<img src="/assets/img/posts/2019-04-13-Human-AI-Competition/Alphago-features.png" alt="AlphaGo Features">

Next it utilizes Reinforcement Learning, letting the network play itself. A policy network, which determines which moves lead to the highest probability of winning and a value network, which measures the strategic value of a board layout.

2016 - AlphaGo defeats Lee Sedol, the world Go champion, 4-1.

<img src="/assets/img/posts/2019-04-13-Human-AI-Competition/Sedol-Alphago.jpg" alt="Lee Sedol and Alphago">

Today - OpenAI Five, a 5v5 team of bots, defeats OG, Dota 2 world champions.

<img src="/assets/img/posts/2019-04-13-Human-AI-Competition/OpenAI-Five.jpg" alt="OpenAI Five">

OpenAI Five are five neural nets which take as input 20,000 numbers. These numbers are an encoding of the visible game state in Dota, or all the information a human player would have. Actions are chosen by the output of the net, a list of eight numbers. The Five also utilizes self-play to generate gameplay data like AlphaGo, using rewards to inform the [Proximal Policy Optimization](https://openai.com/blog/openai-baselines-ppo/) algorithm.
