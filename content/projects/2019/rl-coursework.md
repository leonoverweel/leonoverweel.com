---
title: "Reinforcement Learning Soccer Bots"
date: 2019-03-29

tags:
- language-Python
- ml-NumPy
- ml-PyTorch
- model-Deep-Q-Network
- tool-Git
- tool-GitHub
categories:
- machine-learning

description: "Implemented and tuned eight different reinforcement learning algorithms to play a simple soccer game."
---

This project was the coursework for the [Reinforcement Learning (RL) course](https://www.inf.ed.ac.uk/teaching/courses/rl/) I took as part of my MSc Artificial Intelligence at the University of Edinburgh. In a mix of several simple stochastic environments and the (deprecated) [LARG/HFO](https://github.com/LARG/HFO) half-field offense soccer environment, I implemented eight different reinforcement learning algorithms.

For the following algorithms, I followed pseudocode from [Sutton and Barto (2018)][sutton2018reinforcement]:

* **Dynamic Programming**: Value iteration (page 83).
* **Monte Carlo**: On-policy first-visit MC control for \\(\epsilon\\)-soft policies (page 101).
* **SARSA**: On-policy temporal-difference control (page 130).
* **Q-Learning**: Off-policy temporal-difference control (page 131).

The following algorithm was quite difficult because it involved training a single network using multiple parallel agents each playing in a copy of the HFO environment:

* **Deep Q-Learning**: Asynchronous 1-step Q-learning with function approximation, from [Mnih et al. (2016)][mnih2016asynchronous]; also involved implementing Hogwild parallized stochastic gradient descent from [Recht et al. (2011)][recht2011hogwild].

Finally, these algorithms were in a two-agent setting:

* **Independent Q-Learning**: The same algorithm as Q-learning, but with a joint state representation for the two agents.
* **Joint-Action Learning**: Based on table 4 from [Bowling and Veloso (2001a)][bowling2001multiagent].
* **Wolf-PHC**: Based on tables 1 and 2 from [Bowling and Veloso (2001b)][bowling2001rational].

I built my implementation on top of [this provided base code](https://github.com/raharrasy/RL2019-BaseCodes/tree/9b22e4e0f6802c09845651b79cac602f675c6942), but I can't share my own code. Most of my implementations reached the highest performance threshold defined by the coursework markers.

[bowling2001multiagent]: http://www.cs.cmu.edu/~mmv/papers/02aij-mike.pdf
[bowling2001rational]: http://www.cs.cmu.edu/~mmv/papers/01ijcai-mike.pdf
[mnih2016asynchronous]: https://arxiv.org/abs/1602.01783
[recht2011hogwild]: https://papers.nips.cc/paper/4390-hogwild-a-lock-free-approach-to-parallelizing-stochastic-gradient-descent
[sutton2018reinforcement]: http://incompleteideas.net/book/the-book-2nd.html
