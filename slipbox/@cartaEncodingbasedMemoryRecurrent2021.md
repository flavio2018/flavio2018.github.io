---
title: Encoding-based memory for recurrent neural networks
aliases: ["Encoding-based memory for recurrent neural networks"]
authors: Antonio Carta, Alessandro Sperduti, Davide Bacciu
year: 2021
abstract: 
---
# Encoding-based memory for recurrent neural networks

<p style="text-align: right">
<a href="https://linkinghub.elsevier.com/retrieve/pii/S0925231221005932">
<i>
Antonio Carta, Alessandro Sperduti, Davide Bacciu, 2021</i>
</a>
</p>

***

- main topic: improving on Short-Term Memory capacity
- main claims:
	- proposing a new version of Linear Memory Network where the memory is a Linear Auto-Encoder for Sequences
	- showing a training algorithm for the memory component that enables efficient encoding of the network's hidden states;
	- experiments show that: (a) the encoding method is better than static encodings, and (b) the STM capacity of the network is better than that of RNN and LSTM

***

- in this paper they propose an updated version of the Linear Memory Network that is cited in [[@cartaShortTermMemoryOptimization2020|Short-Term Memory Optimization in Recurrent Neural Networks by Autoencoder-Based Initialization]]
- in the introduction of the paper the authors make explicit reference to the theoretical framework mentioned by Sperduti[^meeting], i.e. they claim that recurrent modules can be separated into two submodules corresponding to two subtasks they are trained to solve. The first submodule is a functional module, whose purpose is to extract task-wide features; the second submodule is a memory module whose purpose is to memorize task-relevant information in the sequence.
	- I'm not completely convinced by the thesis, but maybe I didn't get it well enough
	- the purpose of functional module can be best understood thinking of the neural networks as function approximators; its purpose is then to learn to approximate the function that solves the task 
- The advantage is, once again, that the memory module can be trained separately in ways that are less prone to gradient vanishing problems.
- The authors claim that
	> there is a tradeoff between the expressiveness and nonlinearity of a recurrent model (ability to solve the functional subtask) and its ability to learn long-term dependencies (memorization subtask).
- In par. 2.4 the authors review how this tradeoff is actually impacting different recurrent architectures. It's interesting to see gated architectures (LSTM, GRU) as architectures that partially separates the functional and the memory subtasks, seeing the gates as small memories. These architectures cannot learn long sequences anyway.
- a small reference to MANN simply states that they are hard to train and are susceptible to hyperparameters tuning. Also, they say it's hard to evaluate the performance of the memory component of MANN, differently from the one proposed and based on encodings. 

[^meeting]: [[meeting-supervisors-a]]