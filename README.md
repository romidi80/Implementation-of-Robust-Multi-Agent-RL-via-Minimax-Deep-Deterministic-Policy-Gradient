# Implementation-of-Robust-Multi-Agent-RL-via-Minimax-Deep-Deterministic-Policy-Gradient-
The algorithm described in the M3DDPG publication was fully implemented and tested  within the provided environment.

The selected algorithm for implementation is called DDPG3M, which bears a strong resemblance to the MADDPG algorithm. In this report, we will first delve into an explanation of the MADDPG algorithm, followed by highlighting the differences between the two algorithms.

## Explanation of the MADDPG Algorithm
The MADDPG algorithm falls under the category of multi-agent (Agent Multi) algorithms in continuous Markov decision spaces. In this algorithm, agents, similar to other MDP-based algorithms, explore the environment through interactions with it, taking actions based on observations. After each episode, as in other RL Deep learning methods, the value Q for each state is learned during the process.

MADDPG, like many Critic-Actor algorithms, is divided into two parts: Actor and Critic. The Actor is responsible for selecting actions based on the state, often utilizing a neural network to map states to actions. The chosen actions are sent to the environment, resulting in new states and rewards. This process involves calculating returns for various actions.

Different implementations of the MADDPG algorithm for similar problems often differ in the specifics of their network structures, such as Value Q or Loss for Actor or Critic networks. The pseudo-code of the MADDPG algorithm, along with its specific definitions, is provided below.

## DDPG3M Algorithm
The DDPG3M algorithm introduces a key difference compared to MADDPG. Instead of calculating the return value, it considers the value of the next state using the Minimax algorithm. This means that, instead of explicitly calculating the return value, we aim to minimize the value of the next state based on the Minimax algorithm, which leads to the addition of values for the next-step actions. Consequently, the minimization of the next state value is achieved. These values are obtained by considering the Q values for the next state, incorporating the α gradient factor into the minimization process. Since this function is learned by a neural network, the gradient value is equal to the Value Q learning function or, in other words, the Critic network's Loss. The pseudo-code of the DDPG3M algorithm is provided below.

![image](https://github.com/romidi80/Implementation-of-Robust-Multi-Agent-RL-via-Minimax-Deep-Deterministic-Policy-Gradient/assets/89667194/375fd8fb-2752-4c00-b684-a5b6014c8d4e)
