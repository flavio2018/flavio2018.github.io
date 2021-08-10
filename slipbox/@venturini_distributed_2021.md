---
title: Distributed Reinforcement Learning for Flexible and Efficient UAV Swarm Control
aliases: ["Distributed Reinforcement Learning for Flexible and Efficient UAV Swarm Control"]
authors: Federico Venturini, Federico Mason, Francesco Pase, Federico Chiariotti, Alberto Testolin, Andrea Zanella, Michele Zorzi
year: 2021
abstract: 
---
# Distributed Reinforcement Learning for Flexible and Efficient UAV Swarm Control
<p style="text-align: right"><i>IEEE Transactions on Cognitive Communications and Networking, 2021</i></p>

*Federico Venturini, Federico Mason, Francesco Pase, Federico Chiariotti, Alberto Testolin, Andrea Zanella, Michele Zorzi*

[Resource on the Web](https://ieeexplore.ieee.org/document/9366781/)

---

-   _p.1_ The goal of the paper is to propose a MARL setting and learning algorithm to solve the problem of efficiently coordinate a swarm of drones which needs to discover the position of objects in a 2D map, while partially observing the environment, needing to avoid collisions and obstacles, and being able to communicate over a shared radio channel.
    
-   _p.2_ The problem is framed as a Network-Distributed Partially Observable Markov Decision Process.
    
-   _p.6_ The RL algorithm proposed is a Distributed DQL, namely a single DQN whose parameters are shared among agents in the learning phase. Furthermore, replay memory and training and policy networks are used, with each agent sharing its experience with others by contributing to a single replay memory which all agents sample from to optimze their parameters.