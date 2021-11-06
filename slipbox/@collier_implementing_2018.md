---
title: Implementing Neural Turing Machines
aliases: ["Implementing Neural Turing Machines"]
authors: Mark Collier, Joeran Beel
year: 2018
abstract: Neural Turing Machines (NTMs) are an instance of Memory Augmented Neural Networks, a new class of recurrent neural networks which decouple computation from memory by introducing an external memory unit. NTMs have demonstrated superior performance over Long Short-Term Memory Cells in several sequence learning tasks. A number of open source implementations of NTMs exist but are unstable during training and/or fail to replicate the reported performance of NTMs. This paper presents the details of our successful implementation of a NTM. Our implementation learns to solve three sequential learning tasks from the original NTM paper. We find that the choice of memory contents initialization scheme is crucial in successfully implementing a NTM. Networks with memory contents initialized to small constant values converge on average 2 times faster than the next best memory contents initialization scheme.
---
# Implementing Neural Turing Machines

<p style="text-align: right">
<a href="
http://arxiv.org/abs/1807.08518
">
<i>
Mark Collier, Joeran Beel, 2018</i>
</a>
</p>

***