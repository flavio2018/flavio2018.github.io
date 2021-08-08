---
title: Prioritized Experience Replay
aliases: ["Prioritized Experience Replay"]
authors: Tom Schaul, John Quan, Ioannis Antonoglou, David Silver
year: 2016
abstract: Experience replay lets online reinforcement learning agents remember and reuse experiences from the past. In prior work, experience transitions were uniformly sampled from a replay memory. However, this approach simply replays transitions at the same frequency that they were originally experienced, regardless of their significance. In this paper we develop a framework for prioritizing experience, so as to replay important transitions more frequently, and therefore learn more efficiently. We use prioritized experience replay in Deep Q-Networks (DQN), a reinforcement learning algorithm that achieved human-level performance across many Atari games. DQN with prioritized experience replay achieves a new state-of-the-art, outperforming DQN with uniform replay on 41 out of 49 games.
---
# Prioritized Experience Replay
<p style="text-align: right"><i>arXiv:1511.05952 [cs], 2016</i></p>

*Tom Schaul, John Quan, Ioannis Antonoglou, David Silver*

[Resource on the Web](http://arxiv.org/abs/1511.05952)

---

- The authors consider the common case in RL in which rewards are very sparse and are given only at the end of a sequence of actions that give no reward or punishment. In this context, being able to choose samples from the replay memory somewhat proportionally to the expected improving in loss optimization they can cause is intuitively beneficial.
- Choosing the transition that can cause the best possible learning step is in practice impossible. A proxy for this measure is the TD error which Q-learning is already based on.
- Hence, the authors propose to sample in some way proportionately to the TD error $\delta$ associated to each transition, assigning to new transitions that don't have corresponding error yet the maximal priority. The basic formula of the proabability associated to each sample they propose is $p_k^\alpha \over \sum p_k^\alpha$, and has two variants based on how $p_k$ is defined.
 	- $p_k = 1/R$, where $R$ is the rank of the experience according to the TD
 	- $p_k = |\delta| + \epsilon$, where $\epsilon$ is a stochastic quantity and $\alpha \geq 0$, with $\alpha = 0$ equivalent to the uniform case.
- to implement this kind of weighted sampling in practice, the ECDF over the samples can be approximated with a step function, having constant probability values for fixed intervals of $p_k$ values. In this way, we can pick $m$ samples from each interval and compose batches that always contain the same proportion of samples of each "priority interval". 