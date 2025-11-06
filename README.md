# 🚀 Deep Q-Learning for Lunar Landing 🌕

This project implements a **Deep Q-Learning (DQN)** agent to solve the **LunarLander** environment from **Gymnasium**.  
The mission: 🛰️ train an AI pilot that learns to land a spacecraft safely on a designated landing pad using **reinforcement learning**.

---

## 🧠 Key Concepts & Features

- 💡 **Reinforcement Learning (RL):**  
  The agent learns through *trial and error* — receiving **rewards** for good actions (landing smoothly) and **penalties** for bad ones (crashing 💥).

- 🤖 **Deep Q-Learning (DQN):**  
  Uses a **neural network** to approximate the optimal Q-function, predicting the expected future reward for each possible action.

- 🧩 **Neural Network Architecture:**  
  A **feed-forward network** maps environment states → Q-values for all actions.

- 🔁 **Experience Replay:**  
  Stores past experiences `(state, action, reward, next_state, done)` in a **replay buffer**, sampling random batches for **stable training**.

- 🎯 **Target Network:**  
  A second network used to compute target Q-values — updated periodically to **stabilize** learning.

- ⚖️ **Epsilon-Greedy Policy:**  
  Balances **exploration** (trying new things) and **exploitation** (using what it’s learned), with **epsilon decaying** over time.

- 🌊 **Soft Updates:**  
  Smoothly updates target network weights to prevent oscillations during learning.

- ⚙️ **Optimizer:**  
  Uses **Adam** optimizer and **Mean Squared Error (MSE)** loss for weight updates.

---

## 📦 Dependencies

These key libraries are required for the project:

| Library | Version | Purpose |
|----------|----------|----------|
| 🧩 Gymnasium | 1.2.2 | Environment simulation (`LunarLander`) |
| 🔥 PyTorch | latest (CUDA compatible) | Deep learning models |
| 🔢 NumPy | 2.0.2 | Numerical operations |
| ⚙️ Box2D-py | 2.3.5 | Physics engine |
| 🧰 SWIG | 4.4.0 | Dependency for Box2D |
| 🎥 Imageio | — | For saving gameplay videos |
| 📊 Matplotlib | — | For training score plots |

---



