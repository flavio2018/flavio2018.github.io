---
title: Incremental Training of a Recurrent Neural Network Exploiting a Multi-Scale Dynamic Memory
aliases: ["Incremental Training of a Recurrent Neural Network Exploiting a Multi-Scale Dynamic Memory"]
authors: Antonio Carta, Alessandro Sperduti, Davide Bacciu
year: 2021
abstract: 
---
# Incremental Training of a Recurrent Neural Network Exploiting a Multi-Scale Dynamic Memory

<p style="text-align: right">
<a href="https://link.springer.com/10.1007/978-3-030-67658-2_39">
<i>
Antonio Carta, Alessandro Sperduti, Davide Bacciu, 2021</i>
</a>
</p>

***

- main topic: memorization abilities of recurrent networks using memories that work at different time scales
- main claims: 
	- introducing an extension of RNN that splits the hidden states into several modules, each (pre)trained to encode the hidden states of the network sampled at different frequencies.
	- proposing a learning algorithm that introduces a new module at a time, each sampling the hidden state at a higher level of detail (slower frequency)
	- experiments show that long-term dependency learning in RNNs is improved with this kind of modular memories

***

- the building blocks of the architecture proposed are, once again, the Linear Memory Network (the first version, cited in [[@cartaShortTermMemoryOptimization2020|Short-Term Memory Optimization in Recurrent Neural Networks by Autoencoder-Based Initialization]]) and the Linear Auto-Encoder for Sequences proposed by Sperduti.
- The architecture is basically a LMN with *k* memories, each using only the hidden representations built *t* steps earlier, with *t* varying.
- The role of the LAES in the architecture is to pretrain the memory modules. Since the learning procedure incrementally adds the memory modules, the weights of the new ones are obtained training a LAES to encode the hidden activations of the current model. The connections are then fine-tuned with SGD.