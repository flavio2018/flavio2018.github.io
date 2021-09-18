---
title: Deep Reinforcement Learning Pong from Pixels
aliases: ["Deep Reinforcement Learning: Pong from Pixels"]
authors: Andrej Karpathy
year: 
abstract: 
tags: ["#v/learning/reinforcement"]
---
# Deep Reinforcement Learning: Pong from Pixels

<p style="text-align: right">
<a href="
http://karpathy.github.io/2016/05/31/rl/
">
<i>Andrej Karpathy's blog, 2016</i>
</a>
</p>

*Andrej Karpathy*

---

- first key point: major progress in RL in last years (i.e. ATARI and Go papers, ~2015) do not come out of research about new algorithms but rather on improvements in data sources, infrastructure, computing power - similarly as it already happened in computer vision in ~2012.
	- note: Karpathy states this but does not get deeper in what the advancements in computing power/infrastructure/data sources have been
- learn from the best: 
	- read Sutton Book
	- follow David Silver's course and
	- John Schulman's lectures
- Policy Gradients (PG) is a more effective technique ("when tuned well") to solve RL problems than DQNs.
- credit assignment problem: in Pong we have a very sparse reward (i.e. only +1 if you win, -1 if you lose).
- parallel with supervised learning: in supervised learning you immediately have a feedback about the algorithm's performance, comparing the output to a label, which makes it possible to immediately update weights, depending on their gradient and on the correctness of the output.
- With Policy Gradient methods you can still compute the gradients of the parameters that generated the actions chosen at each timestep, but you will need to wait until the end of the episode (when you get the only possible reward +/-1) to use the gradients to modify the parameters to increase or decrease the probability of occurrence of those actions
	- how do we use *all* the gradients relative to the actions taken in an episode to modify the values of the weights?
- Karpathy explains the Policy Gradient methods using some metaphor that is more related to writing backpropagation code than to the intuitive idea of optimizing the network weights. Then, however, he moves to a different metaphor: while in simple reinforcement learning we are optimizing $\sum_i log p(y_i|x_i)$ where $y_i$ are the correct labels, in the PG case we are optimizing $\sum_i A_i · log p(y_i|x_i)$ where $A_i$ is the advantage given by the action $y_i$ (could be the reward at the end of the episode, or a discounted sum of future rewards), and $x_i$ is some input to our policy approximator (i.e. ANN). Multiplying by the advantage and maximizing that function makes so that the probability of actions that had a bad outcome is minimized, since the corresponding terms will be negative, while the probability of good actions is maximized. 
- He even goes on to give a hint of the math beneath: the general idea is that we want to maximize the expected reward of some action. The action is chosen according to the policy approximated by our network, so we ideally want to modify weights so that the sampled action is more likely to lead to a good reward. Mathematically:
$\nabla_{\theta}\mathbb{E}_{x \sim p(x|\theta)} [f(x)]=\mathbb{E}[f(x)\nabla_{\theta}log p(x)]$
, where $f$ is the reward function evaluating our actions and because of some mathematical simplifications.
This motivates adding the multiplication by the advantage as explained above.
- [John Schulman's lecture on the topic](https://www.youtube.com/watch?v=oPGVsoBonLM)