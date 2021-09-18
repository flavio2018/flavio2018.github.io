---
title: Communicating artificial neural networks develop efficient color-naming systems
aliases: ["Communicating artificial neural networks develop efficient color-naming systems"]
authors: Rahma Chaabouni, Eugene Kharitonov, Emmanuel Dupoux, Marco Baroni
year: 2021
abstract: Words categorize the semantic fields they refer to in ways that maximize communication accuracy while minimizing complexity. Focusing on the well-studied color domain, we show that artificial neural networks trained with deep-learning techniques to play a discrimination game develop communication systems whose distribution on the accuracy/complexity plane closely matches that of human languages. The observed variation among emergent color-naming systems is explained by different degrees of discriminative need, of the sort that might also characterize different human communities. Like human languages, emergent systems show a preference for relatively low-complexity solutions, even at the cost of imperfect communication. We demonstrate next that the nature of the emergent systems crucially depends on communication being discrete (as is human word usage). When continuous message passing is allowed, emergent systems become more complex and eventually less efficient. Our study suggests that efficient semantic categorization is a general property of discrete communication systems, not limited to human language. It suggests moreover that it is exactly the discrete nature of such systems that, acting as a bottleneck, pushes them toward low complexity and optimal efficiency.
tags: ["h/ai"]
---
# Communicating artificial neural networks develop efficient color-naming systems

<p style="text-align: right">
<a href="
http://www.pnas.org/lookup/doi/10.1073/pnas.2016569118
">
<i>Proceedings of the National Academy of Sciences
-
2021</i>
</a>
</p>

*Rahma Chaabouni, Eugene Kharitonov, Emmanuel Dupoux, Marco Baroni*
***


-   _p.1_ One core theory behind the paper is that of Information Bottleneck, a framework developed to study the accuracy _vs_ complexity trade-off in languages. The two extreme cases of systems favouring one aspect over the other are communication systems having only one symbol, and one having as many symbols as referents.
    
-   _p.2_ An interesting point about using DNN models to study human cognition and behaviour. If we observe the emergence of similar behaviour in connectionist models and in humans, we can argue that the two phenomena have common roots. Since we can manipulate agents parts easily, we can build a framework to indentify causal relationships between model parts and emerging behaviours.
    
-   _p.2_ The core point of the article is that the property of efficiency of communication (from an Information Bottleneck perspective) may not be unique to the human language, but rather an emergent property of discrete communication systems developed by communicating cognitive agents.
    
-   _p.2_ The author make the point showing that two agents playing a simple communication game about colours using a discrete communication system, develop a “code” which is similar to human languages w.r.t. its Information Bottleneck profile.
    
-   _p.3_ The task is framed in the following way: the Speaker agent is shown a coloured chip and creates a probability distribution over its vocabulary; then, a word is sampled according to such distribution. The word is received by the Listener agent, to which are showed two coloured chips, the original one and a confounding one. Based on the received word and the two chips observed, the Listener agents outputs a probability distribution over the two position of the chips representing its confidence about the position that the Speaker was indicating (e.g. 0.96 left, 0.04 right).
    
-   _p.5_ There is reported an interesting convergence of results with a very similar study. Another model of emergence of color-naming systems was recently developed, and it showed strikingly similar features to the one presented in this article. This happened despite some differences in the implementation. This could be a further evidence that efficiency and low complexity are emerging features of communication systems developed by DNN agents, disregarding of the implementation detail – provided that the communication channel is discrete.