---
title: "Exploration of Neural Network Learning Algorithms and Regularization"
date: 2018-10-26
aliases:
  - /mlp-1

tags:
- language-python
- ml-numpy
- ml-matplotlib
- model-convolutional-neural-network
- tool-git
- tool-github
categories:
- machine-learning

description: "Implemented and experimented with different learning rules, learning rate schedules, and regularization techniques to train a convolutional neural network for the EMNIST handwritten character recognition task."
---

For the [first coursework](http://www.inf.ed.ac.uk/teaching/courses/mlp/2018-19/mlp_cw1_2018-19.pdf) of the [Machine Learning Practical (MLP)](http://web.archive.org/web/20190411171457/http://www.inf.ed.ac.uk/teaching/courses/mlp/index-2018.html) course I took as part of my MSc Artificial Intelligence at the University of Edinburgh, we experimented with different ways of traiming a convolutional neural network to recognize handwritten digits in the [EMNIST dataset](https://www.nist.gov/node/1298471/emnist-dataset).

I implemented and experimented with the following variations from the baseline:

* Two to five hidden layers. I kept this constant at three for other experiments.
* Different learning rules: standard stochastic gradient descent, RMSProp (slide 26 in [Tieleman and Hinton (2012)][tieleman2012rmsprop]), and Adam (algorithm 1 in [Kingma and Ba (2015)][kingma2015adam]).
* Different learning rate schedules: a constant learning rate and cosine annealing with and without warm restarts (equation 7 in [Loshchilov and Hutter (2017)][loshchilov2017decoupled]).
* Different regularization methods: L2 regularization and weight decay.

I also experimented with different hyperparameter settings for different combinations of these variations. From my experiments, I concluded that the Adam rule worked best for a three-layer model, and that L2 regularization helped speed up learning.

For more details, including training curves and results tables, see my full report below (or [download it as PDF](/pdfs/uoe-mlp-1.pdf)).

<embed class="pdf" src="/pdfs/uoe-mlp-1.pdf" alt="pdf" pluginspage="http://www.adobe.com/products/acrobat/readstep2.html">

One thing I learned from this coursework is that I should have been plotting training curves for both the training and validation data sets as well, since training set curves alone do not say much about whether the model is still learning generalizable information. Another is that I should only report final performance on the test set, not training curves.

Please note that my report above is reproduced as-is, and does not incorporate these learnings. My next coursework for MLP does incorporate them.

[loshchilov2017decoupled]: https://arxiv.org/abs/1711.05101
[tieleman2012rmsprop]: https://www.cs.toronto.edu/~tijmen/csc321/slides/lecture_slides_lec6.pdf
[kingma2015adam]: https://arxiv.org/abs/1412.6980
