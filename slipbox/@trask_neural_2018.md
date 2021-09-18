---
title: Neural Arithmetic Logic Units
aliases: ["Neural Arithmetic Logic Units"]
authors: Andrew Trask, Felix Hill, Scott Reed, Jack Rae, Chris Dyer, Phil Blunsom
year: 2018
abstract: Neural networks can learn to represent and manipulate numerical information, but they seldom generalize well outside of the range of numerical values encountered during training. To encourage more systematic numerical extrapolation, we propose an architecture that represents numerical quantities as linear activations which are manipulated using primitive arithmetic operators, controlled by learned gates. We call this module a neural arithmetic logic unit (NALU), by analogy to the arithmetic logic unit in traditional processors. Experiments show that NALU-enhanced neural networks can learn to track time, perform arithmetic over images of numbers, translate numerical language into real-valued scalars, execute computer code, and count objects in images. In contrast to conventional architectures, we obtain substantially better generalization both inside and outside of the range of numerical values encountered during training, often extrapolating orders of magnitude beyond trained numerical ranges.
---
# Neural Arithmetic Logic Units

<p style="text-align: right">
<a href="
http://arxiv.org/abs/1808.00508
">
<i>arXiv, 2018</i>
</a>
</p>

*Andrew Trask, Felix Hill, Scott Reed, Jack Rae, Chris Dyer, Phil Blunsom*

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