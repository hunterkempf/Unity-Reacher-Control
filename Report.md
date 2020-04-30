# Report

## Algorithm chosen

For this Project I chose the DDPG (Deep Deterministic Policy Gradients) algorithm outlined in the following paper https://arxiv.org/abs/1509.02971. 

The basic idea of DDPG is to have both an Actor network and a Critic Network that allows one network to focus on the Q-values (Critic) and the other network to focus on the State to Action mapping. 

## Training Results

<div style="text-align:center"><img src="/TrainingScores.png" /></div>

Since this model was trained with 20 agents all running the same exact code I included for each episode of training a Max, Min and average as well as the rolling 100 episode average. My implementation took 215 episodes for the 100 episode rolling average to meet the threshold of 30 which on my computer took 86.93 minutes to run.

## Model Implementation

Actor (3 fully connected layers first 2 with relu activations and the last with tanh activation):

State Vector (33) --> fully connected layer (33->128) --> relu (128 -> 128) --> fully connected layer (128 -> 128) --> relu (128 -> 128) --> fully connected layer (128 -> 4) --> tanh (4 -> 4) --> Action Vector (4)

Critic (3 fully connected layers first 2 with relu activations and the last linear activation):

State Vector (33) --> fully connected layer (33->128) --> relu (128 -> 128) + add in the action values -->  fully connected layer (132->128) --> relu (128 -> 128) --> fully connected layer (128 -> 1) --> Expected Reward Vector (1)

## Other Attempted Model Implementations

Actor and Critic with 128 --> 64 neurons Took 577 Episodes and 221.09 minutes to reach the threshold of 30


Actor and Critic with 64 --> 64 neurons Never Converged after 330 episodes and started falling down

Actor and Critic with 256 --> 256 neurons Took ___ Episodes and ___ minutes to reach the threshold of 30

## Future Improvements

I used the DDPG algorithm to solve this problem which has the benefit of being more simple to understand and code but it does not allow individual agents to learn on their own and thus wastes some of the potential of the 20 arm environment. To improve this algorithm I would explore a dynamic weight for the soft update parameter TAU (larger at the beginning and smaller at the end) to potentially learn faster. I also think changing the model number of connected layers and neurons could yeild improved performance.

Algorithms like PPO, A3C, and D4PG that use multiple (non-interacting, parallel) copies of the same agent to distribute the task of gathering experience would be a really interesting future improvement to this project.
