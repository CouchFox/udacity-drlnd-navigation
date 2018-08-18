[//]: # (Image References)

[image1]: plot.png "Plot of Rewards"
[image2]: trained-agent.gif "Trained Agent"

# Project 1: Navigation Report
Here you can see a short clip of the trained agent in action:
![Trained Agent][image2]
### Learning Algorithm
For this project a DQN (Deep Q-Network) was chosen as a learning algorithm (as showcased in an earlier excercise). As opposed to the solution by deepmind who used a convolutional model (as for the atari challenges they chose a pixel to action approach) in the project here the model is a simple neural network with just 2 hidden layers because the 37 states are known to the agent - and there is no need to train an image recognition during the training phase too.

#### Network model
For the network model the same model was chosen as in the dqn exercise. It consists of a simple pytorch model with two hidden layers each consisting of 64 nodes (changing those to 128 didn't imporve the learning ability of the agent, so it was left at 64).

#### Hyperparameters
Model:
* hidden layers in model: 2 (unchanged from dqn exercise)
* nodes in hidden layers in model: 64 (unchanged from dqn exercise)

Agent:
* replay buffer size (BUFFER_SIZE) : int(1e5)  needs to be high enough to sample enough experiences
* minibatch size (BATCH_SIZE) : 64  (seems to be a good default value. increasing to 128 didn't improve performance)      
* discount factor (GAMMA) : 0.99   (unchanged with good results)
* soft update of target parameters (TAU) : 1e-3  (unchanged with good results)
* learning rate (LR) = 5e-4   (needs to be small enough. further decreasing didn't help though)
* network updates (UPDATE_EVERY) : 4   (unchanged with good results)


### Plot of Rewards
With the chosen network model, dqn agent and python code in the jupyter notebook, the system was able to achieve an average score of 13 in 508 episodes:
![Plot of Rewards][image1]

### Ideas for Future Work
* add code for the pixel to action version of the project. This would require the network model to have convolution layers to work with the image input
* create a unity game from scratch and use a dqn to solve it (s. also https://github.com/CouchFox/scifi-buttons-ml-agent for the entry to the first unity ml agent challenge )
* improve the dqn with the following extensions:
  * Double dqn
  * Prioritized experience replay
  * Dueling dqn
  * Distributional dqn
  * Noisy dqn
  * Rainbow (all of the above)
