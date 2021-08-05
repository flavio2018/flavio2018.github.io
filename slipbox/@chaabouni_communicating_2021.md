---
title: Communicating artificial neural networks develop efficient color-naming systems
authors: Rahma Chaabouni, Eugene Kharitonov, Emmanuel Dupoux, Marco Baroni
year: 2021
---

Communicating ANN Develop Efficient Color Naming
---

-   _p.1_ One core theory behind the paper is that of Information Bottleneck, a framework developed to study the accuracy _vs_ complexity trade-off in languages. The two extreme cases of systems favouring one aspect over the other are communication systems having only one symbol, and one having as many symbols as referents.
    
-   _p.2_ An interesting point about using DNN models to study human cognition and behaviour. If we observe the emergence of similar behaviour in connectionist models and in humans, we can argue that the two phenomena have common roots. Since we can manipulate agents parts easily, we can build a framework to indentify causal relationships between model parts and emerging behaviours.
    
-   _p.2_ The core point of the article is that the property of efficiency of communication (from an Information Bottleneck perspective) may not be unique to the human language, but rather an emergent property of discrete communication systems developed by communicating cognitive agents.
    
-   _p.2_ The author make the point showing that two agents playing a simple communication game about colours using a discrete communication system, develop a “code” which is similar to human languages w.r.t. its Information Bottleneck profile.
    
-   _p.3_ The task is framed in the following way: the Speaker agent is shown a coloured chip and creates a probability distribution over its vocabulary; then, a word is sampled according to such distribution. The word is received by the Listener agent, to which are showed two coloured chips, the original one and a confounding one. Based on the received word and the two chips observed, the Listener agents outputs a probability distribution over the two position of the chips representing its confidence about the position that the Speaker was indicating (e.g. 0.96 left, 0.04 right).
    
-   _p.5_ There is reported an interesting convergence of results with a very similar study. Another model of emergence of color-naming systems was recently developed, and it showed strikingly similar features to the one presented in this article. This happened despite some differences in the implementation. This could be a further evidence that efficiency and low complexity are emerging features of communication systems developed by DNN agents, disregarding of the implementation detail – provided that the communication channel is discrete.