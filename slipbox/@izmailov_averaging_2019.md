---
title: Averaging Weights Leads to Wider Optima and Better Generalization
aliases: ["Averaging Weights Leads to Wider Optima and Better Generalization"]
authors: Pavel Izmailov, Dmitrii Podoprikhin, Timur Garipov, Dmitry Vetrov, Andrew Gordon Wilson
year: 2019
abstract: Deep neural networks are typically trained by optimizing a loss function with an SGD variant, in conjunction with a decaying learning rate, until convergence. We show that simple averaging of multiple points along the trajectory of SGD, with a cyclical or constant learning rate, leads to better generalization than conventional training. We also show that this Stochastic Weight Averaging (SWA) procedure finds much flatter solutions than SGD, and approximates the recent Fast Geometric Ensembling (FGE) approach with a single model. Using SWA we achieve notable improvement in test accuracy over conventional SGD training on a range of state-of-the-art residual networks, PyramidNets, DenseNets, and Shake-Shake networks on CIFAR-10, CIFAR-100, and ImageNet. In short, SWA is extremely easy to implement, improves generalization, and has almost no computational overhead.
---
# Averaging Weights Leads to Wider Optima and Better Generalization
<p style="text-align: right"><i>arXiv:1803.05407 [cs, stat], 2019</i></p>

*Pavel Izmailov, Dmitrii Podoprikhin, Timur Garipov, Dmitry Vetrov, Andrew Gordon Wilson*

[Resource on the Web](http://arxiv.org/abs/1803.05407)

---

[Implemented in PyTorch](/https://pytorch.org/docs/stable/optim.html).