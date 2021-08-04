## 3.3 Learning framework
- Reinforcement Learning
	- Deep Q-Learning
	- Policy & Target Networks
	- Replay memory
	- Curriculum learning

---

In the agent-based setting described so far, the most natural choice for a learning framework is that of reinforcement learning. This kind of learning algorithms have been applied for a long time to problems in the fields of artificial intelligence and robotics, obtaining more recently impressive results in the area of games learning ([@mnih_human-level_2015](@mnih_human-level_2015.md), [@mnih_human-level_2015](@mnih_human-level_2015.md)) thanks to the effective adaptation of reinforcement learning algorithms to deep learning settings.

### Markov Decision Processes
Reinforcement learning settings usually involve one *agent* situated in an *environment* in which it can perform some *actions*. The environment will change it *state* as a result of the agent's actions, and the agent will also receive a (positive or negative) *reward* based on the outcome of its action in a specific environment state. 

The setting described above involving these two entities (agent and environment) is called a Markov Decision Process (MDP). If a MDP is *finite*, the sets of states, actions and reward values are all finite. In this setting the transition process from a state to the following one, and the reward received by the agent in the next timestep, are completely determined by the action taken by the agent and on the current state. Indeed, the reward received and the state reached after an action can be formally described as random variables, having a discrete probability distribution that only depends on the action and state of the environment:
$r \in R \subset \mathbb{R} , s\in S$
$r: A \times S → [0,1]$
$s: A \times S → [0,1]$,
where $S$ and $R$ are the finite sets of possible environment states and rewards.

The fact that the states visited by the agent in previous timesteps and the actions taken therein do not influence future rewards and state transitions makes the process *Markovian*. A state that contains information about all the aspects of the agent-environment interactions in past timesteps that are relevant for future transitions and rewards is said to have the *Markov property*.

It is worth noticing that the MDPs are a very general and powerful tool to describe goal-directed decision making problems:

> The MDP framework is a considerable abstraction of the problem of goal-directed learning from interaction. It proposes that whatever the details of the sensory, memory, and control apparatus, and whatever objective one is trying to achieve, any problem of learning goal-directed behavior can be reduced to three signals passing back and forth between an agent and its environment: one signal to represent the choices made by the agent (the actions), one signal to represent the basis on which the choices are made (the states), and one signal to define the agent’s goal (the rewards). [@mnih_human-level_2015](@mnih_human-level_2015.md)

![RL](file:///media/shift97/My%20Passport/Flavio/Unipd/Tesi/figures/reinforcement_learning.png)
*The agent–environment interaction in a Markov decision process.*

Informally, we can say that the goal of the agent in the learning process is to maximize the cumulative rewards received in the future. Taking into account future rewards other than the immediate reward received after taking an action reflects the fact that the action taken at a timestep also (indirectly) influence future states visited by the agent and, therefore, the possible future rewards of the agent. Usually, future rewards are *discounted*, i.e. they are given less weight in the learning process with respect to rewards closer to an action in time.

The actions taken in a specific environment state at a given timestep are chosen by the agent according to a function called a *policy*. It is a probability distribution over all actions, given the current state of the environment: $\pi_{s}: A → [0,1]$. Reinforcement learning algorithms specify how the agent's policy changes as a result of experience.

Usually, reinforcement learning algorithms also include the estimation of *value functions*, i.e. the agent's estimate of how good it is to be in a given state, or to take an action in a given state. The estimation of the value of states and actions of course depends on the rewards received by the agent in the past in similar situations. Since future rewards depend on the future states that the agent will be able to reach from a given state after performing an action, value functions usually depend on policies.

An important result regarding finite MDPs is that we can define a partial ordering on the possible policies depending on the corresponding action value function. Formally: 
$\pi \geq \pi' \iff v_{\pi}(s) \geq v_{\pi'}(s) \forall s \in S$.
Therefore, we can always identify one policy or a group of policies that are *optimal*, in the sense that they are greater or equal to all other policies according to the partial ordering defined above. If there are more than one, the optimal policies $\pi_*$ all share the same action value function $v_*(s)$, called the optimal value function, defined as:
$v_*(s) := max_{\pi} v_{\pi}(s), \forall s \in S$. 
Optimal policies also share the optimal state-action value function, defined as: 
$q_*(s, a) := max_{\pi} q_{\pi}(s, a), \forall s \in S, a \in A$. 
For each state-action pair, $q_*$ defines the value as the sum of the next future reward and the estimate of the reached state value according to the optimal action value function:
$q_*(s,a) = \mathbb{E}[R_{t+1} + \gamma v_*(S_{t+1}) | S_t=s, A_t=a]$.

### Q-Learning
One of the first reinforcement learning algorithms to have been adapted to the deep learning setting is Q-Learning ([@mnih_human-level_2015](@mnih_human-level_2015.md), [@mnih_human-level_2015](@mnih_human-level_2015.md)). This algorithm is, in its original form, a model-free and off-policy reinforcement learning algorithm, which means that it does not rely on a model of the environment, and that the policy function is not directly modeled by the algorithm but is rather implicit in the creation of a state-action value function called *Q-function*.

The core idea behind the algorithm is that trying all possible actions in every state over many episodes, the agent can ultimately learn to estimate the state-action value function for each state-action pair, based on the reward received when it makes each action, and its estimate of the value of the state it reaches. The main theoretical result behind the algorithm states that it will converge to the optimal Q-function if it will be given the possibility to experience every possible state-action pair virtually infinitely many times. *However, this is considered a weak condition, since...*

The Q function is assumed to be represented in a table. The equation which is used to update the values of the function is:
    
$Q( A_t, S_t ) ← Q( A_t, S_t ) + \alpha [R( S_{t+1} ) + \gamma · \max_a Q(S_{t+1}, a) - Q( A_t, S_t )]$

where $A_t$ and $S_t$ are the current action and state, and $S_{t+1}$ is the state the agent reaches performing action $A_t$. We see that the agent takes into account both the reward given to it in the new state and its estimate on the best possible value of the state it reaches.

Q-Learning is only applicable to Markovian processes; we can notice that counting with the aid of an external representation *can be* defined as a Markovian process, provided that the "rules" of any arbitrary syntax to produce symbols to represent numerosity are known to the agent.