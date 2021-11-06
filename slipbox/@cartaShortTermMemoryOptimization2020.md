---
title: Short-Term Memory Optimization in Recurrent Neural Networks by Autoencoder-Based Initialization
aliases: ["Short-Term Memory Optimization in Recurrent Neural Networks by Autoencoder-Based Initialization"]
authors: Antonio Carta, Alessandro Sperduti, Davide Bacciu
year: 2020
abstract: Training RNNs to learn long-term dependencies is difficult due to vanishing gradients. We explore an alternative solution based on explicit memorization using linear autoencoders for sequences, which allows to maximize the short-term memory and that can be solved with a closed-form solution without backpropagation. We introduce an initialization schema that pretrains the weights of a recurrent neural network to approximate the linear autoencoder of the input sequences and we show how such pretraining can better support solving hard classification tasks with long sequences. We test our approach on sequential and permuted MNIST. We show that the proposed approach achieves a much lower reconstruction error for long sequences and a better gradient propagation during the finetuning phase.
---
# Short-Term Memory Optimization in Recurrent Neural Networks by Autoencoder-Based Initialization

<p style="text-align: right">
<a href="http://arxiv.org/abs/2011.02886">
<i>
Antonio Carta, Alessandro Sperduti, Davide Bacciu, 2020</i>
</a>
</p>

***

- main topic: an alternative (to backprop) way to train RNNs
- main claims:
	- if we use a weight initialization schema that makes the RNN approximate a linear autoencoder for sequences,
	- we can reach (a) lower reconstruction error on long sequences, and
	- (b) better gradient propagation in the finetuning phase (dealing with vanishing gradient problem)

***

- another viewpoint of the work is that they propose to use Short Term Memory (STM) capacity as a training goal instead of learning long-term dependencies.
	- the thing is, RNN trained with backprop cannot efficiently learn to represent long sequences, but LAES do, despite the two are similar tasks[^laes-notes]
- the main advantage of the approach is that given the input sequences the weights of the linear autoencoder can be found analytically; therefore, you just need then to pretrain the network  to approximate those weights
- the linear autoencoder for sequences (LAES) was proposed in another work by Sperduti and Pasa.
- the LAES cannot be reproduced using a standard recurrent network with nonlinear activations. 
Therefore, they use another model already proposed by Carta and Bacciu called Linear Memory Network, which has the peculiarity to build an hidden state *h* and a memory state *m*, the first updated with non-linear activations and the second with linear ones.

[^laes-notes]: [[172-laes-notes]]