# Reinforcement Learning

Reinforcement learning (RL) trains an **agent** to act in an **environment** so as to maximize cumulative reward. Unlike supervised learning, there are no labeled answers — only a reward signal and the consequences of actions.

## The Markov Decision Process

RL is formalized as an MDP \\((\mathcal{S}, \mathcal{A}, P, R, \gamma)\\): states, actions, transition probabilities \\(P(s'|s,a)\\), reward \\(R\\), and discount factor \\(\gamma\in[0,1)\\). The agent seeks a **policy** \\(\pi(a|s)\\) maximizing the expected return
\\[
G_t = \sum_{k=0}^{\infty}\gamma^k R_{t+k+1}.
\\]

## Value Functions and Bellman Equations

\\[
V^\pi(s) = \mathbb{E}_\pi[G_t \mid S_t = s], \qquad Q^\pi(s,a) = \mathbb{E}_\pi[G_t \mid S_t=s, A_t=a].
\\]
The optimal value obeys the **Bellman optimality equation**:
\\[
Q^*(s,a) = \mathbb{E}\big[R + \gamma\max_{a'} Q^*(s', a')\big].
\\]
This is dynamic programming — closely related to [Optimal Control](../../eng/control/optimal.md).

## Core Algorithms

| Method | Idea |
|---|---|
| Value iteration / policy iteration | exact DP when the model is known |
| **Q-learning** | off-policy temporal-difference control |
| SARSA | on-policy TD control |
| Policy gradient (REINFORCE) | optimize \\(\pi_\theta\\) directly via \\(\nabla_\theta J\\) |
| Actor–Critic / PPO | combine value and policy learning; stable, scalable |

### Q-Learning Update

\\[
Q(s,a) \leftarrow Q(s,a) + \alpha\big[r + \gamma\max_{a'}Q(s',a') - Q(s,a)\big].
\\]

## Exploration vs. Exploitation

The agent must explore to discover rewards yet exploit what it knows. Strategies: \\(\varepsilon\\)-greedy, softmax/Boltzmann, optimism under uncertainty (UCB), and entropy bonuses.

## Deep RL

Replacing tables with neural-network function approximators gives **DQN** (Atari), **PPO/SAC** (continuous control, robotics), and AlphaGo-style search + RL. Sample efficiency, stability, and reward design remain central challenges.

## Applications

Robotics and locomotion, game playing, recommendation, resource scheduling, and RL from human feedback (RLHF) for aligning language models.

## Example: Tabular Q-Learning Skeleton

```python
import numpy as np

def q_learning(env, episodes=500, alpha=0.1, gamma=0.99, eps=0.1):
    Q = np.zeros((env.n_states, env.n_actions))
    for _ in range(episodes):
        s = env.reset()
        done = False
        while not done:
            a = np.random.randint(env.n_actions) if np.random.rand() < eps else Q[s].argmax()
            s2, r, done = env.step(a)
            Q[s, a] += alpha * (r + gamma * Q[s2].max() - Q[s, a])
            s = s2
    return Q
```

## See Also

- [Optimal Control](../../eng/control/optimal.md)
- [Bayesian Inference](../../math/probability/bayes.md)
- [Robot Control](../../app/robotics/control.md)
