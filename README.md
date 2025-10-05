# Maze-World Reinforcement Learning

This repository implements and analyzes **on-policy temporal-difference control methods**—SARSA(λ), SARSA, and Expected SARSA—on a stochastic Maze-World environment with shaped rewards, obstacles, and slip dynamics.

## Overview

A baseline SARSA(λ) agent is realized with:

- Standard backward-view update  
- Per-episode trace reset  
- Replacing traces  
- Fixed exponential ε-decay  

An improved SARSA(λ) variant is introduced to stabilize multi-step credit assignment:

1. **Per-state trace clearing** – only the most recent action at a state maintains eligibility, reducing action-trace competition.  
2. **Optional Expected SARSA(λ) backup** – lowers target variance by using the ε-greedy expectation.  
3. **Optional Q-value clipping** – guards against value spikes under stochastic transitions.  
4. **Modestly reduced learning rate** – balances bias and variance.

## Results

- Under matched protocols (identical layouts, ε schedules, and budgets), the improved SARSA(λ) achieves **perfect or near-perfect success**.  
- Last-100 average returns improve over one-step SARSA.  
- The gap to Expected SARSA is reduced.  
- Behavioral diagnostics—greedy path visualizations and average path lengths under slip—show smoother, more direct trajectories to the goal.

## Implementation

- Two single-file Python implementations provide a **transparent, reproducible, and extensible platform** for studying eligibility-trace design and expected backups in stochastic GridWorlds.  
- The repository includes:  
  - Training scripts  
  - Greedy path plotting  
  - Path-length evaluation under slip  
  - Smoothed return curves  


