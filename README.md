# Deep Q-Learning for Lunar Landing

This project implements a Deep Q-Learning (DQN) agent designed to solve the LunarLander-v3 environment from Gymnasium. The goal is to train an agent that can successfully land a spacecraft on a designated landing pad using reinforcement learning.

## Key Concepts and Features:

*   **Reinforcement Learning (RL):** The agent learns by interacting with the environment, receiving rewards for desired actions (like moving towards the landing pad) and penalties for undesirable ones (like crashing).
*   **Deep Q-Learning (DQN):** Utilizes a neural network to approximate the optimal Q-function, estimating the expected future reward for taking a specific action in a given state.
*   **Neural Network Architecture:** A feed-forward neural network maps the environment's state to predicted Q-values for each possible action.
*   **Experience Replay:** Stores experiences (state, action, reward, next state, done) in a replay buffer, sampling random batches for stable training.
*   **Target Network:** A separate network used to calculate target Q-values, updated periodically to stabilize training.
*   **Epsilon-Greedy Policy:** Balances exploration (trying new actions) and exploitation (choosing the action with the highest predicted Q-value), with epsilon decaying over time.
*   **Soft Updates:** Gradual updating of the target network's weights to further stabilize training.
*   **Adam Optimizer:** Used to update neural network weights based on the Mean Squared Error loss.

## Dependencies:

The following key libraries are used in this project:

*   **Gymnasium**: `1.2.2` (Environment simulation, specifically `LunarLander-v3`)
*   **PyTorch**: (for deep learning models, versions depend on CUDA setup)
*   **NumPy**: `2.0.2` (numerical operations)
*   **Box2D-py**: `2.3.5` (physics engine for `LunarLander`)
*   **SWIG**: `4.4.0` (Simplified Wrapper and Interface Generator, dependency for Box2D)
*   **Imageio**: (for saving video outputs)
*   **Matplotlib**: (for plotting training scores)

## Setup and Installation:

To set up the environment and install the necessary libraries, run the following commands:

```bash
!pip install gymnasium
!pip install "gymnasium[atari, accept-rom-license]"
!apt-get install -y swig
!pip install gymnasium[box2d]
```

## Usage:

1.  **Import Libraries:** The notebook begins by importing essential libraries such as `torch`, `torch.nn`, `torch.optim`, `gymnasium`, and `collections`.
2.  **Build the AI:** A `Network` class defines the neural network architecture for the Q-function approximation.
3.  **Train the AI:**
    *   The `LunarLander-v3` environment is initialized.
    *   Hyperparameters like learning rate, minibatch size, discount factor, and epsilon decay are set.
    *   The `ReplayMemory` class implements experience replay.
    *   The `Agent` class encapsulates the DQN algorithm, including `act`, `step`, `learn`, and `soft_update` methods.
    *   The agent is trained over a specified number of episodes, balancing exploration and exploitation. Training stops when an average score of 200.0 over 100 consecutive episodes is achieved.
4.  **Visualize Results:** After training, the agent's performance can be visualized by generating a video of it playing the game. The trained model checkpoint is saved as `checkpoint.pth`.

## Training Results:

The training process logs the average score over the last 100 episodes. The agent successfully solves the environment when this average score reaches 200.0. A plot of the average score vs. episodes is also generated to show the learning progress.

Example output from training:

```
Episode 100\tAverage Score: -153.77
Episode 200\tAverage Score: -100.25
Episode 300\tAverage Score: -56.82
Episode 400\tAverage Score: -24.33
Episode 500\tAverage Score: 90.48
Episode 593\tAverage Score: 200.98
Environment solved in 493 episodes!\tAverage Score: 200.98
```

## Saved Model:

Upon successful training, the trained agent's local Q-network state dictionary is saved as `checkpoint.pth`.
