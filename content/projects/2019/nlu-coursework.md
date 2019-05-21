---
title: "Neural Machine Translation with Lexical Model"
date: 2019-03-14

tags:
- language-Python
- ml-Matplotlib
- ml-NumPy
- ml-PyTorch
- model-Long-Short-Term-Memory
- tool-Git
- tool-GitHub
categories:
- machine-learning

description: "Analyzed a neural machine translation architecture, and implemented and evaluated a lexical model on top of it."
---

This project was the second coursework for the [Natural Language Understanding, Generation, and Machine Translation (NLU+) course](https://course.inf.ed.ac.uk/nlu+/) I took as part of my MSc Artificial Intelligence at the University of Edinburgh. The assignment focused on Japanese to English neural machine translation (NMT) and consisted of several parts:

1. Understanding the baseline implementation, an encoder-decoder  bi-directional long short-term memory network (as implemented in [nmt_toolkit](https://github.com/demelin/nmt_toolkit)).[^partner]
1. Exploring the model further, looking into things like replacing greedy search with beam search and experimenting with adding more layers.
1. Implementing and evaluating the lexical model proposed by [Nguyen and Chiang (2017)][nguyen2017improving] (Section 4).

Here's the architecture of the model I used for experiments with the lexical model:

{{< figure src="/images/projects/2019/nlu-coursework/architecture.png" caption="Diagram of the NMT system architecture with a 2-layer encoder (bi- directional LSTMs) and a 3-layer decoder (LSTMs). Figure made in [draw.io](https://draw.io) and adapted from [Britz et al. (2017)](https://arxiv.org/abs/1703.03906)." >}}

The lexical model by [Nguyen and Chiang (2017)][nguyen2017improving] is meant to improve the translation of rare words. Attention-based NMT systems suffer from the fact that attention takes into account the context of previously translated target words, which means it will sometimes favor words that fit well within the context of the translation so far, but that do not correspond to the source word being translated. The lexical model attempts to solve this by jointly training an extra feed-forward network that generates target words purely based on the source word. See Section 4 of [Nguyen and Chiang (2017)][nguyen2017improving] for a more detailed explanation.

For the assignment, we used a fraction of the data and computing power generally available to NMT researchers (I trained on my laptop for a few hours instead of many GPUs for two weeks), so the results were not very good in an absolute sense compared to the state of the art (order of ~30 BLEU). In the relative sense, though, my implementation of the lexical model improved the NMT system's performance significantly: the [BLEU score](https://en.wikipedia.org/wiki/BLEU) went from 7.98 to 10.90 and perplexity went from 22.4 to 20.0. 

You can check out my code on GitHub: [leonoverweel/infr-1157-nlu](https://github.com/leonoverweel/infr-11157-nlu/tree/master/coursework-2). My full report, with much more analysis, is [available here](/pdfs/uoe-nlu-2.pdf) and embedded below:

<embed class="pdf" src="/pdfs/uoe-nlu-2.pdf" alt="pdf" pluginspage="http://www.adobe.com/products/acrobat/readstep2.html">


[^partner]: I did this part together with a partner, before we both continued on our own. 

[nguyen2017improving]: https://arxiv.org/abs/1710.01329