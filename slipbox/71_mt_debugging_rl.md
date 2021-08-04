# Scenario
Let's have well clear in mind what our current scenario is.

The **reward function** can be currently composed of the following components:
- [ ] positive reward for correct label
- [ ] negative reward for wrong labels
- [ ] constant small negative reward
- [x] small positive rewards for visiting unseen states

We are not giving hints about *how to solve* the task to the agent.

The **environment dynamics** are currently the following:
- the episode ends after a fixed number (10) of timesteps, or when the agent outputs the right label

# Theory
- Q: what is the optimal policy that the agent is guaranteed to learn with Q-Learning? [[58_mt_learning_framework#Markov Decision Processes]]
A: the one that guarantees maximum long term reward (e.g. 0.9 per each episode in my simple setting. However, this does not always happen at least in the DQN case; is this a problem of ANN training convergence? How to deal with it?)
- do we represent the state meaningfully enough? [[@sutton_reinforcement_2018#p 50]]
	- are we building the state representation with the NN (visual representation hidden state)?

[Under what mathematical conditions will Q Learning learn?](http://www.cs.cmu.edu/afs/cs.cmu.edu/project/learn-43/lib/photoz/.g/web/glossary/converge.html)	

# Practice
[86_how_write_unit_tests](86_how_write_unit_tests.md)

---

## Silvester's suggestions
- lower replay memory capacity for communication problems (old experience is outdated)
- [x] `lr 1e-3 1e-4`
- [x] compute average rewards during learning (plot average reward curve)

fixed environment:
- `./log/20210713-121134`

best up to now:
- `tensorboard --logdir ./log/20210714-101708`
```
|     1     |     0.84     |
|     2     |    0.786     |
|     3     |     1.0      | 
```
- 256 hidden units and 1.5e-3 learning rate did not outperform previous setting in terms of accuracy, but the learning profile was similar (maybe learning was slower?) `tensorboard --logdir ./log/20210714-161631`

### Different sized objects
- convergence with up to 3 objects of variable size `tensorboard --logdir ./log/20210716-151948`
- convergence with up to 4 objects of variable size `tensorboard --logdir ./log/20210726-171908`
```
+-----------+--------------+
| # objects | avg accuracy |
+-----------+--------------+
|     1     |     1.0      |
|     2     |    0.996     |
|     3     |    0.998     |
|     4     |     1.0      |
+-----------+--------------+
```