# Deep Q-learning
from [pytorch tutorial](https://pytorch.org/tutorials/intermediate/reinforcement_q_learning.html)

- ==note==: our environment is deterministic, so the expectations in the Q-learning and TD learning formulas disappear.
- the network is trained to approximate Q*
- we use the fact that, for any policy, the Q function associated to the policy obeys the Bellman equation
- we train the network minimizing sum of temporal difference errors
- we use the Huber Loss as an objective function
	- this is more appropriate since in the beginning of training the estimates are more noisy

Recently[^fedus], the role of replay memory when training an agent with Q-learning has been reviewed.

[^fedus]: [@fedus_revisiting_2020](@fedus_revisiting_2020.md)