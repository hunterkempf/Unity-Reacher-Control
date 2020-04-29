# Report

## Algorithm chosen

For this Project I chose the DDPG algorithm outlined in the following paper https://arxiv.org/abs/1509.02971. 

The basic idea of DDPG is to have both an Actor network and a Critic Network that allows one network to focus on the Q-values (Critic) and the other network to focus on the State to Action mapping. 

## Training Results

<div style="text-align:center"><img src="/TrainingScores.gif" /></div>

## Model Implementation

Actor (3 fully connected layers first 2 with relu activations and the last with tanh activation):

State Vector (33) --> fully connected layer (33->128) --> relu (128 -> 128) --> fully connected layer (128 -> 128) --> relu (128 -> 128) --> fully connected layer (128 -> 4) --> tanh (4 -> 4) --> Action Vector (4)

Critic (3 fully connected layers first 2 with relu activations and the last linear activation):

State Vector (33) --> fully connected layer (33->128) --> relu (128 -> 128) + add in the action values -->  fully connected layer (132->128) --> relu (128 -> 128) --> fully connected layer (128 -> 1) --> Expected Reward Vector (1)

## Future Improvements

I used the DDPG algorithm to solve this problem which has the benefit of being more simple to understand and code but it does not allow individual agents to learn on their own and thus wastes some of the potential of the 20 arm environment.

Algorithms like PPO, A3C, and D4PG that use multiple (non-interacting, parallel) copies of the same agent to distribute the task of gathering experience would be a really interesting future improvement to this project.
