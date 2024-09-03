# Deep Q-Learning Implementations in GridWorld

This Jupyter Notebook contains two implementations of Deep Q-Learning (DQN) for a simple GridWorld environment: a **Basic DQN** and an **Advanced DQN** that incorporates a target network and experience replay buffer. The implementations demonstrate how reinforcement learning can be applied to solve a grid-based navigation problem.

## Table of Contents
1. [Introduction](#introduction)
2. [Requirements](#requirements)
3. [Basic DQN](#basic-dqn)
4. [Advanced DQN](#advanced-dqn)
5. [Usage](#usage)
6. [Results](#results)


## Introduction

The **GridWorld** environment is a 4x4 grid where an agent starts at the top-left corner and aims to reach the bottom-right corner. The agent receives a reward of `-1` for each step taken until it reaches the goal, where it receives a reward of `0`. 

The notebook includes:
- A basic DQN implementation that learns to navigate the GridWorld using a simple neural network.
- An advanced DQN implementation that uses a target network and experience replay to stabilize training and improve performance.

## Requirements

To run the notebook, you need the following Python packages:
- `torch`
- `numpy`
- `matplotlib`

## Basic DQN

The **Basic DQN** implementation uses a single neural network to approximate the Q-values for each action. The agent explores the environment and learns from its experiences using the Q-learning algorithm.

### Key Features:
- Simple feedforward neural network with two hidden layers.
- Epsilon-greedy policy for exploration.
- Mean Squared Error loss function for training.

### Code Overview:
The basic DQN implementation is encapsulated in the `train_model()` function, which initializes the environment, trains the agent, and plots the total rewards per episode.

## Advanced DQN

The **Advanced DQN** implementation enhances the basic DQN by introducing:
- **Target Network**: A separate network that stabilizes training by providing fixed Q-value estimates for the next state during updates.
- **Experience Replay**: A buffer that stores past experiences, allowing the agent to learn from a diverse set of experiences and break the correlation between consecutive experiences.

### Key Features:
- Uses a target network updated every few episodes.
- Implements an experience replay buffer for sampling past experiences.
- Maintains the same structure as the basic DQN, with added complexity for improved performance.

### Code Overview:
The advanced DQN implementation follows a similar structure to the basic one but includes additional logic for managing the target network and experience replay.

## Usage

1. Open the Jupyter Notebook in your preferred environment.
2. Run the cells sequentially to execute the code for both the basic and advanced DQN implementations.
3. Observe the output and the plots generated for total rewards per episode.

## Results

After training, the notebook will generate plots showing the total rewards obtained by the agent in each episode. You should observe that the advanced DQN generally performs better than the basic DQN due to the added stability from the target network and experience replay.
