---
title: Reservoir stack machines
aliases: ["Reservoir stack machines"]
authors: Benjamin Paaßen, Alexander Schulz, Barbara Hammer
year: 2021
abstract: 
---
# Reservoir stack machines

<p style="text-align: right">
<a href="
https://linkinghub.elsevier.com/retrieve/pii/S0925231221011103
">
<i>
Benjamin Paaßen, Alexander Schulz, Barbara Hammer, 2021</i>
</a>
</p>

***

[code](https://gitlab.com/bpaassen/reservoir_stack_machines)

Main topic: an alternative architecture to solve algorithmic tasks.

Main claims: 
- presentation of a new architecture, the "reservoir stack machine", a network that uses a stack as external memory
- presentation of a training algorithm that consists in only training the last layer of the recurrent network
- the architecture achieves zero-error on NTM benchmark tasks and on context-free languages
- the network can generalize to sequences longer than observed
- the network can be trained fast with few examples

***

The authors propose another model[^paassen] that is easier to train than a NTM and performs comparably well.

MANN are proposed to help models solve tasks in which memory must be separated from computation; i.e., when information needs to be stored without being corrupted for later use. I can see a parallel with external memory systems and human memory: to solve some tasks we need to have external tools, or at least *mental tools*.

The architecture presented can be inserted in the framework of reservoir computing[^comparison]. The core idea of reservoir computing is to use a randomly initialized network that is kept untrained but has guaranteed Short-Term Memory (STM) properties.

The architecture is, in particular, an Echo State Network, «combined with an explicit stack that can store information without interference».

The authors use a trick to train the network to use the stack: they provide the network examples of read and write operations on the external memory, by labeling the examples with this additional information. This reduces the problem «to a classification problem that can be solved with convex optimization in seconds instead of minutes to hours».

Much of the paper is dedicated to parallels between theoretical computer science and Reservoir computing. The approach is not intended to be applicable IRL since the labels for the use of memory are hardly found. However, the imitation learning parallel is reasonable from a cognitive perspective.


[^comparison]: notice that a useful comparison of different frameworks including also reservoir computing is in [[@cartaEncodingbasedMemoryRecurrent2021|Encoding-based memory for recurrent neural networks]]
[^paassen]: [[@paassen_reservoir_2021|Reservoir Memory Machines as Neural Computers]] and this paper are both an extension of another previous work, [[@paassenReservoirMemoryMachines2020|Reservoir memory machines]]