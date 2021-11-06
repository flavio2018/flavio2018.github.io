---
title: Attention and Augmented Recurrent Neural Networks
aliases: ["Attention and Augmented Recurrent Neural Networks"]
authors: Chris Olah, Shan Carter
year: 2016
abstract: A visual overview of neural attention, and the powerful extensions of neural networks being built on top of it.
---
# Attention and Augmented Recurrent Neural Networks

<p style="text-align: right">
<a href="
http://distill.pub/2016/augmented-rnns
">
<i>Distill
-
2016</i>
</a>
</p>

*Chris Olah, Shan Carter*
***

- there have been four main directions in which RNNs have been tried to be enhanced: Neural Turing Machines, Attentional Interfaces, Adaptive Computation Time and Neural Programmers. They all rely on attention mechanisms.
- the main thing about NTMs is that the recurrent cell is able to read and write from an external memory at each step, which contains vectors. So, at time *t* other than receiving an element of the input sequence and the internal representation built in the previous step, it also receives a vector read from the memory.
- The main point is that the reading and writing operations should be differentiable, in particular with respect to the position of memory access. In this way, the network can learn *where* to read and write.
- The difficulty is that we intuitively think about positions in a discrete way. Instead, NTMs define a *distribution of attention* across the whole memory. As a result, when e.g. reading, the vector read is a weighted sum of all vectors in memory.
	- Is "make everything continuous" a general principle in deep learning?
- When writing in memory, the distribution of attentions describes where and by how much we overwrite the previous content in memory.
- The attention distribution is formed in three steps: first, the controller outputs a query vector which is dot-multiplied by all vectors in the memory to find the most similar. Then, the similarity vector (a proto- attention distribution) is interpolated with the previous attention vector, and then it is convolved with a shift filter, allowing the controller to move its attention to nearby locations.
- The result of this ability in practice is that networks can e.g. learn to store sequences in memory and then replay them in the future.
- > *Interacting with media naturally involves making a sequence of taking an action, observing, and taking more actions. This creates a major challenge: how do we learn which actions to take? ... The wonderful thing about attention is that it gives us an easier way out of this problem by partially taking all actions to varying extents.*
	- (unlike in reinforcement learning settings where action selection could stay in a discrete space.)
- A proposed comparison metaphor between reinforcement learning and NTMs is that while in RL we unfold many experience pathways one at a time and then learn from them, in NTMs we take and evaluate all pathways at once.
- One major problem of NTMs is that the computational cost of their training grows linearly with the size of the memory. Indeed, if we want to build the attention distribution based on our current memory contents, we currently have no easy way to do that if not looking at all memory positions at each timestep. Therefore, learning to efficiently read and write from a big memory can take a long computational time.