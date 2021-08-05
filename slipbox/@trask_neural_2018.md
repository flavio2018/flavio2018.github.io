---
title: Neural Arithmetic Logic Units
authors: Andrew Trask, Felix Hill, Scott Reed, Jack Rae, Chris Dyer, Phil Blunsom
year: 2018
---

Neural Arithmetic Logic Units
---

-   _p.1_ Basic idea: two modules specifically designed to solve simple arithmetic operations (algebraic sum, multiplication, power)
    
-   _p.1_ The model uses neurons to encode quantities without nonlinearities. This is because they observed that, to learn the identity function, a MLP without nonlinearities outperformed MLPs with nonlinear activations
    
-   _p.2_ The paper presents structured experimental evidence of the issue of learning exact numerosity as a higher level feature of the input
    
-   _p.2_ The sum is modeled as a matrix product with a modified weight matrix, forced to take values within \[-1, 1\] and close to {-1, 0, 1}
    
-   _p.3_ Multiplication is modeled using a unit which uses exp and log functions, as well as the same matrix used for the sum
    
-   _p.4_ The limits of the model, from a cognitive modeling PoV, are explicitely stated at the end of par. 3: the model precisely estimates numerosity disregarding of the magnitude of the input, whereas in real cognitive tasks acuity decreases where input magnitude increases
    
-   _p.4_ The tasks on which the models were trained and tested on are: learning simple arithmetic functions directly from raw numbers or from images; temporal tasks, such as textual representation of numbers translation; a simple reinforcement learning task requirinig to keep track of time; etc.

---

The model designed by Trask et al. is able to learn functions and other number-based operations which generalize well over unseen number intervals.  
  
However, the model is specifically engineered to learn such numerical relations, and is not very insightful from a cognitive modeling perspective.  
  
Specifically, the ability of the model to encode exact numerosity in individual neurons is in contrast with the empirical evidence of decreasing acuity corresponding to increasing magnitude found in numerosity estimation tasks in humans and mammals.