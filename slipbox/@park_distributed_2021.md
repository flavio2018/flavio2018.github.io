---
title: Distributed associative memory network with memory refreshing loss
aliases: ["Distributed associative memory network with memory refreshing loss"]
authors: Taewon Park, Inchul Choi, Minho Lee
year: 2021
abstract: 
---
# Distributed associative memory network with memory refreshing loss

<p style="text-align: right">
<a href="
https://linkinghub.elsevier.com/retrieve/pii/S0893608021003014
">
<i>
Taewon Park, Inchul Choi, Minho Lee, 2021</i>
</a>
</p>

***

Main topic: improving the relational reasoning abilities of MANN

Main claims:
- introducing a new kind of memory architecture, the Distributed Associative Memory (DAM)
- introducing the Memory Refreshing Loss (MRL) task
- the MRL improves the relational reasoning abilities of MANN without using self-attention

***

This work introduces a different kind of external memory architecture, which the authors claim to be inspired by the functioning of the human brain.

This work could be compared (and is compared by the authors) to [[@raeScalingMemoryAugmentedNeural2016 1|Scaling Memory-Augmented Neural Networks with Sparse Reads and Writes]].

Parallels with human brain · The main parallels with the human brain are (a) that items are distributed across several memory blocks rather than in one single memory slot, and (b) that the memorization is enhanced with a "refreshing" mechanism (MRL) which mimics some rehearsing procedure happening in the brain.

MRL · This is a task which the authors propose to use as an additional task to train the network on in a multi-task learning setting. This is motivated by a psychological background, i.e. evidence that if a person is simultaneously trained to solve a task and repeat number or words that are useful in the task, the memory performance is enhanced. Similarly, the task encoded in the MRL consists in forcing the network to reproduce inputs based on its current memory contents.

Relational reasoning · The example provided for relational reasoning is the BaBI task, i.e. the synthetic language reasoning task which DNC was also tested on. It contains short sentences of the form (subject-verb-predicate). Other tasks the memory was tested on are *Nth* farthest[^n-farthest] and the convex hull[^hull] tasks. The memory is also tested on the baseline copy and associative recall tasks.

Efficiency · Although on some tasks the model has a performance comparable to that of other DNC-derived models, the authors highlight that it is more efficient since it does not employ self-attention mechanisms.

[^hull]: given a list of points in 2D find *k* that form a convex hull
[^n-farthest]: find the Nth farthest vector from a given one