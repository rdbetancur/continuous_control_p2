## Context

The challenge of this project is to ensure that the agent (20 double-jointed arms) maintain its position at the target location for as many time steps as possible. A reward of +0.1 is provided for each step that the agent's hand is in the goal location.

The program was developed with the DDPG algorithm, based on the course code (https://github.com/udacity/deep-reinforcement-learning/tree/master/ddpg-pendulum).
In the project folder is the Unity environment (Reacher.app), the Jupyter file to run and two files with the Actor (Policy) Model, the Critic (Value) Model and the Agent. 
In the model use 2 fully connected hidden layers with ReLu activations for both the actor and the critic with a configuration of 256 nodes in each of them.

Tanh is used in the final layer that maps states to actions. Batch normalization is used for mini batch training. Mirar https://pytorch.org/docs/stable/nn.html#normalization-layers 

## Agent Hyper Parameters

	•	BUFFER_SIZE = int(1e6)  # replay buffer size
	•	BATCH_SIZE = 256        # minibatch size
	•	GAMMA = 0.99            # discount factor
	•	TAU = 1e-3              # for soft update of target parameters
	•	LR_ACTOR = 1e-3         # learning rate of the actor 
	•	LR_CRITIC = 1e-3        # learning rate of the critic
	•	WEIGHT_DECAY = 0        # L2 weight decay
	•	TI_STEPS = 20           # timesteps 
	•	NU_PASS = 10            # number of passes
	•	EPSILON = 1.0           # epsilon for noise process
	•	EPSILON_DECAY = 1e-6    # decay rate for noise process

## Performance and Plot of Rewards

https://github.com/rubenbet/continuous_control_p2/blob/master/Results.png

The Environment was solved in 86 episodes.

Average Score Episode 20: 0.99
Average Score Episode 40: 2.28
Average Score Episode 60: 4.95
Average Score Episode 80: 21.47
Average Score Episode 100: 37.59
Average Score Episode 120: 39.24
Average Score Episode 140: 38.59
Average Score Episode 160: 37.34
Average Score Episode 180: 36.92
Average Score Episode 200: 37.83

## Improvements

There is a very interesting article that gives some future programming alternatives: In this paper (CEM-RL: COMBINING EVOLUTIONARY AND GRADIENT-BASED METHODS FOR POLICY SEARCH), they propose a different combination scheme using the simple cross-entropy method (CEM) and Twin Delayed Deep Deterministic policy gradient (TD3), another off-policy deep RL algorithm which improves over DDPG. They evaluate the resulting method, CEM-RL, on a set of benchmarks classically used in deep RL. They show that CEM-RL benefits from several advantages over its competitors and offers a satisfactory trade-off between performance and sample efficiency (https://openreview.net/pdf?id=BkeU5j0ctQ). 
