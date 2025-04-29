# Taxi Reinforcement Learning Agents

## Overview
This project applies reinforcement learning techniques to solve the **Taxi-v3 environment** from OpenAI Gymnasium.  
I implemented and compared two approaches:
- **SARSA (State-Action-Reward-State-Action)** — a classical tabular reinforcement learning method.
- **Deep Q-Network (DQN)** — a deep learning-based method using neural networks to approximate the Q-function.

The goal was to train an agent capable of picking up and dropping off passengers at the correct locations efficiently while maximizing cumulative rewards.


## Algorithms Implemented
- **SARSA Agent**  
  - Learns the Q-values by updating based on the action actually taken (on-policy learning).
  - Utilizes an epsilon-greedy exploration strategy with decaying epsilon over episodes.
  - Stores Q-values in a lookup table for all state-action pairs.

- **Deep Q-Network (DQN) Agent**  
  - Approximates the Q-function using a neural network.
  - Uses experience replay and target networks to stabilize learning.
  - Trained using the Stable-Baselines3 library with both default and fine-tuned hyperparameters.


## Environment Details
- **Environment**: [Taxi-v3](https://www.gymlibrary.dev/environments/toy_text/taxi/)
- **State Space**: 500 discrete states (taxi position, passenger location, destination)
- **Action Space**: 6 discrete actions (move south, north, east, west, pickup, dropoff)


## Training and Evaluation

### SARSA Agent
- Trained for **20,000 episodes**.
- Achieved a **total reward of 13** in simulation.
- Learned a stable and optimal policy using epsilon decay.

### DQN Agent
- Trained with two configurations:
  - **Default Training**: 500,000 timesteps.
  - **Optimized Training**: 1,000,000 timesteps with fine-tuned hyperparameters.
- Evaluation Results:

| Model | Mean Reward | Standard Deviation |
|:------|:------------|:-------------------|
| DQN (500K Steps) | 8.4 | 2.58 |
| DQN (1M Steps, Optimized) | 9.1 | 3.01 |


## Results Summary

- **SARSA** achieved **more stable learning** and **better performance** for this small-scale problem compared to DQN.
- **DQN** required significantly longer training and was computationally heavier, sometimes struggling with stability during learning.
- **Final conclusion**: For smaller environments with discrete state-action spaces like Taxi-v3, **tabular methods like SARSA can outperform deep learning-based methods** in terms of both efficiency and stability.
  

## Key Learnings

- **On-policy learning** (SARSA) can be more stable in environments where optimal actions need careful adaptation rather than aggressive exploration.
- **DQN** shows its strengths in **larger or more complex state spaces**, but can be overkill for simple problems.
- **Exploration-exploitation balance** (using epsilon decay) is critical for learning efficient policies.
- **Hyperparameter tuning** plays a major role in reinforcement learning performance.


## Project Structure
```
📂 Reinforcement-Learning-Taxi-Agent/
 ├── Taxi Reinforcement Learning Final Project.ipynb   # Main notebook
 ├── dqn_taxi.zip                                      # Saved default DQN model (optional)
 ├── dqn_taxi_optimal.zip                              # Saved optimized DQN model (optional)
 ├── README.md                                         # Project documentation
```


## Acknowledgements
- OpenAI Gymnasium for providing the Taxi-v3 environment.
- Stable-Baselines3 for simplifying DQN implementation.
- Project developed as part of coursework at The University of Chicago (2024–2025).

---

# 🚖 Happy Reinforcement Learning!
