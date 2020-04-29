# Unity Reacher Control

<div style="text-align:center"><img src="https://github.com/Unity-Technologies/ml-agents/raw/master/docs/images/reacher.png" /></div>

## Background Information
For this Project I built a deep reinforcement learning model to train an robotic arm to track a target location. Visually the task is achieved when the darker blue ball is touching the bright green 'target' ball. 

In this environment, a double-jointed arm can move to target locations. A reward of +0.1 is provided for each step that the agent's hand is in the goal location. Thus, the goal of the agent is to maintain its position at the target location for as many time steps as possible.

The observation space consists of 33 variables corresponding to position, rotation, velocity, and angular velocities of the arm. Each action is a vector with four numbers, corresponding to torque applicable to two joints. 

To learn more about the environment see the Unity link:
https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Learning-Environment-Examples.md#reacher

## Download the Reacher Environment

|Version|Binary|
|-------|-----|
|**_Version 1: One (1) Agent_**|[LINUX](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Linux.zip), [LINUX-NO-VIZ](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Linux_NoVis.zip), [MAC](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher.app.zip), [WIN32](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Windows_x86.zip)|[WIN64](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Windows_x86_64.zip)|
|**_Version 2: Twenty (20) Agents_**|[LINUX](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Linux.zip),[LINUX-NO-VIZ](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Linux_NoVis.zip),  [MAC](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher.app.zip), [WIN32](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Windows_x86.zip), [WIN64](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Windows_x86_64.zip)|
    
(Use LINUX-NO-VIZ for training in headless mode)

## Before Training

<div style="text-align:center"><img src="/Untrained.gif" /></div>

Before Training the agent takes random actions and may sometimes connect with a target by random chance but most of the time the targets are not reached.

## After Training

<div style="text-align:center"><img src="/Final.gif" /></div>

As you can see after training the model achieves pretty good results and is able to track the target in most instances. Part of what makes this a non trivial problem is that there are many different speeds and directions that the target may move. 

## How to Install Requirements

This Project requires Python 3.6.3 due to the tensorflow 1.7.1 requirement in the requirements.txt file. Additionally it requires the Unity Environment and ml-agents package installed https://github.com/Unity-Technologies/ml-agents



# Future Improvements

I used the DDPG algorithm to solve this problem which has the benefit of being more simple to understand and code but it does not allow individual agents to learn on their own and thus wastes some of the potential of the 20 arm environment. 

Algorithms like PPO, A3C, and D4PG that use multiple (non-interacting, parallel) copies of the same agent to distribute the task of gathering experience would be a really interesting future improvement to this project.
