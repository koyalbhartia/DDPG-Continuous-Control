Impelementation of DDPG Reinforcement algorithm for Reacher problem where a double-jointed arm is made to move to target locations.

In this project the second verison of the problem has been solved which contains 20 identical agents, each with its own copy of the environment.
The barrier here is to take into account the presence of many agents. 


Details of environment :
```
Observation space type: continuous
Number of agents : 20
Observation space size (per agent): 33 (Corresponding to position, rotation, velocity, and angular velocities of the arm)
Action space size (per agent): 4 (Corresponding to torque applicable to two joints)
Every entry in the action vector should be a number between -1 and 1.
```

### Reward :

In this environment, a double-jointed arm can move to target locations.
A reward of +0.1 is provided for each step that the agent's hand is in the goal location.
Thus, the goal of your agent is to maintain its position at the target location for as many time steps as possible.
After each episode, we add up the rewards that each agent received (without discounting), to get a score for each agent. This yields 20 (potentially different) scores. We then take the average of these 20 scores.
This yields an average score for each episode (where the average is over all 20 agents).


### Neural Network details :

#### Actor Network

The neural network architecture consists of teh following layers:
1. An input layer of 33 neurons.
2. Hidden layer with 256 neurons
3. Hidden layer with 128 neurons
4. Output layer of 4 neurons 

#### Critic Network

The neural network architecture consists of teh following layers:
1. An input layer of 33 neurons.
2. Hidden layer with 256 + 4 action neurons = 260 neurons
3. Hidden layer with 128 neurons
4. Output layer of 1 neuron 

### Agent details :
```
BATCH_SIZE = 128        # minibatch size
BUFFER_SIZE = int(1e5)  # replay buffer size
GAMMA = 0.99            # discount factor
LR_ACTOR = 1e-4         # learning rate of the actor 
LR_CRITIC = 1e-4        # learning rate of the critic
TAU = 1e-3              # for soft update of target parameters
WEIGHT_DECAY = 0        # L2 weight decay

```

### DDPG parameters.
```
number of episodes=1000, 
Maximum time step per episode =1000,
```
### Implementation

1. Two networks are maintained for each Actor and Critic in order to have a smooth learnings.
2. Actor-Critic model is employed in which the Critic model learns the value function and uses it to determine how the Actor’s policy based model should change.
3. The Actor brings the advantage of learning in continuous actions space without the need for extra layer of optimization procedures required in a value based function while the Critic supplies the Actor with knowledge of the performance.
4. The learning rate for both Actor and Critic is 1e-3 with soft update of target set to the same 1e-3. 
5. A Replay buffer maintains the tuple [State , Action , Reward , Next state , Done ]
6. Optimizer used for back propagation is Adams.
7. Relu is used after every fully connveted layer.
8. We are adding actions in the critic network with the second hidden layer.
10. We use Tau parameter to update the network slowly so that we so not overshoot in gradient descent and function learned by the neural network is better.


## Final Results :

![Episode_score_graph](https://user-images.githubusercontent.com/40532456/124653238-aae18600-de62-11eb-88f1-8561e1d97ed7.png)

Below is the output of how the Avg Reward converged vs Episode number post 100 episodes.

![Episode_reward](https://user-images.githubusercontent.com/40532456/124653488-fa27b680-de62-11eb-8060-513294685417.png)


**The game has been solved with a +30 score on an average of 100 episodes at 112 episodes.**


### Ideas to improve on the results.
1. Different replay buffers can be used for different agents
2. Prioritization of replay buffers.
3. PPO will be a good algotihm to try in this case.
4. Batch size of Replay BUffer can be increased to increase success of learning.
5. We can play with the number of time steps to have a good balance between exploitation and exploration.
