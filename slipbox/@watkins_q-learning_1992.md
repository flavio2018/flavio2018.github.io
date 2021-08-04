---
title: Q-Learning
authors: Christopher J.C.H. Watkins, Peter Dayan
year: 1992
---

Q-Learning
---

-   _p.1_ Q-Learning algorithm can be seen as a form of dynamic programming: why?
    
-   _p.1_ Q-Learning works in Markovian domains, i.e. the transition process from a state to the following one is completely characterized by the stochastic transition function which only depends on the action taken by the agent and on the current state.
    
-   _p.1_ Q-Learning is a model-free method for RL. The core idea is that, trying all actions in all states over many episodes, the agent can ultimately learn to estimate the action-value function for each state-action pair, based on the reward received when it makes each action, and its estimate of the value of the state it reaches.
    
-   _p.2,3_ Q-Learning and the Q action-value function implicitly assume a policy over actions, hence the method is “off-policy”, i.e. independent of the policy implicitly used (_Sutton & Barto, p.153_).
    
-   _p.3_ The Q action-value function is assumed to be represented in a table. The equation which is used to update the values of the function is:
    
	$Q( A, S ) ← Q( A, S ) + \alpha [R( S' ) + \gamma · \max_{a} Q(S', a) - Q( A, S )]$
	
    where $A$ and $S$ are the current action and state, and $S’$ is the state the agent reaches performing action $A$. We see that the agent takes into account both the reward given to it in the new state and its estimate on the best possible value of the state it reaches.
    
-   _p.3_ The algorithm converges only if the agent is given the possibility to explore virtually an infinite number of episodes for each starting state and actions (i.e. explore infinitely many times all combinations of states and actions). This is considered however a weak condition.
    

---

The Q action-value function can be approximated by a DNN. Such network is given the current state as input and outputs the values $Q(S, A_i)$ for all possible actions $A_i$.

-   The learning process of the network consists in minimizing the expected value of the square of the second term in the update rule of the Q function itself (intuitively, we do not want to change the values of the Q function anymore, eventually).
    
-   This process has, however, several problem. First, since the training data come from a virtual environment, they are not i.i.d. as in common DL/ML scenarios. One simple way to overcome this problem is to store past observed situations in an external memory, which is used to estimate the loss function sampling past experiences randomly.
    
-   Secondly, the original loss function is nonstationary (intuitively, since the values of the Q function change, then the mean and std of the loss function change as well, since the loss includes evaluations of the Q function).