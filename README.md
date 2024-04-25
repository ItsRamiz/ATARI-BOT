***WARNING: The code provided requires an external GPU to speed up the learning phase and around 12-16GB of Memory***
***Highly recommended to run on Google Collab before using personal workspace***

Implementation of a Reinforcement Learning agent for the ATARI-Breakout game using Deep Q-Network (DQN) agent which includes Q learning update rule, backproping through a neural network function approximator, an experience replay buffer, and a target network to which the network weights are periodically updated.


**Preprocessing game image:** Raw atari images are large, 210x160x3 by default. However, we don't need that level of detail in order to learn them.
* Resizing to a smaller shape, 64 x 64
* Converting to grayscale
* Cropping irrelevant image parts (top, bottom and edges

**Frame buffer:**
Agent can only process one observation at a time, so we gotta make sure it contains enough information to find optimal actions. For instance, agent has to react to moving objects so he must be able to measure object's velocity.
To do so, we introduce a buffer that stores 4 last images.


**Building a network:**
Built a neural network that can map images to state q-values. This network will be called on every agent's step.

