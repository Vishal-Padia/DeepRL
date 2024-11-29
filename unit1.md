So basically here's how it works:

- Our Agent receives *state S_0* from the environment
- Based on that *state S_0*, the agent takes *action A_0*
- The environment goes to a *new state S_1*
- The environment gives some *reward R_1* to the agent.

This RL Loop output a sequence of statem action, reward, and next state.

The agent's goal is to *maximize* its cumulative reward, called the expected return.

Markov Property

The Markov property implied that our agent needs only the current state to decided what action to take and not the history of all the states and actions they took before.

Observations/State Space

Observations/States are the information our agent gets from the environment. In the case of a video game, it can be a frame. In the case of the trading agent, it can be the value of a certain stock. 

There's a differentiation to make between _observation_ and _state_, however:

- State s: is a complete description of the state of the world (there's not hidden information). In a fully observed environment.

- Observations o: is a partial description of the state. In a partially observed environment.

Action Space:

The action space is the set of all possible actions in an environment. The actions can come from a discrete or continous space:

- Discrete Space: The number of possible actions in Finite. (Mario bros: left, right, up, down)
- Continous Space: The number of possible actions in infinite. (literally everything)

Rewards and the discounting

The rward is fundamental in RL because it's the only feedback for the agent. Thanks to it, our agent knows *if the action taken was good or not.*

The cumulative reward at each time step t can be written as:
R(tau) = r_{t+1} + r_{t+2} + r_{t+3} + ....

However we can't just add them like that. The rewards that come sooner (at the beginning of the game) are more likely to happen since they are more predictedable than the long term future reward.

Types of tasks

A task is an instance of a Reinforcement learning problem. We can have two types of tasks: Episodic and Continuing.

Episodic task:

We have a starting point and ending point (a terminal state). This creates an episode: a list of states, actions, rewards, and new states. (Example: Super Mario Bros, an episode begins at the starts and then ends when you're killed or reached the end of level)

Continuing task:

These are tasks that continue forever (no terminal state). In this case, the agent must learn how to choose the ebst actions and simultaneously interact with the environment. (Automated stock trading: There's no starting point and terminal state)

The Exploration/Exploitation tradeoff:

- Exploration is exploring the environment by trying random actions in order to find more information about the environment.
- Exploitation is exploiting known information to maximize the reward.

Remember the goal of our RL agent is to maximize the expected cumulative reward. However, we can fall into a common trap.

Therefore, we must define a rule that helps to handler this trade-off. We'll see the different ways to handle it in the future results.

The two main approaches for solving RL Problems:

The policy $π$: the agent's brain

It's the brain of our agent, it's the function that tells us what action to take given the state we are in. So it defines the agent's behaviora at a given time.

Our goal is to find the optimal policy $π^*$ through training.

The two approaches to train our agent to find optimal policy:

- Directly, by teaching the agent to learn which action to take, given the current state: *Policy-Based Methods*
- Indirectly, teach the agent to learn which state is more valuable and then take action that leads to the more valuable states: *Value-Based Methods*

Policy Based Methods

In this we learn from a policy function directly.

Its basically like a mapping of each state with it's corresponding action. Alternatively it could define a probability distribution over the set of possible actions at that state.

We have two types of policies:

- Deterministic: a policy at a given state will always return the same action. ( action = policy(state) )
- Stochastic : outputs a probability distribution over actions. ( policy(action|state) = probability distribution over the set of actions given the current state )

Value based methods:

Instead of learning from a policy function, we learn a value function that maps a state to the expected value of being at that state.

The value of state is the expected discounted return the agent can get if it starts in that state, and then acts accordig to our policy.

