- How can Deep Neural Networks learn to manipulate symbols?

My thesis project involves three technical / theoretical aspects:
1. (Multi-Agent) Reinforcement Learning
2. External memories
3. Symbolic reasoning
4. (Emergence of language)

Topics: continual learning,

Compared to my work, the one of Graves et al. does not involve visual processing mechanisms. Also, and relatedly, the model can be used on more general problems. The model exploits the flexibility of the vectorial and matricial formats of representation and manipulation (memory writing/reading).

The model I am developing in the thesis involves the visual-processing side of numerical cognition. The fundamental aspect of the counting problem is, however, its time-dependent and behavioural nature. The use of a grid-like "visual" external representation can be considered a more complex but analogous case to that of using an external memory such as the Grave's one. The side of symbolic reasoning is, however, outside the scope of experiments of Graves et al., as far as I understand. However, McClelland suggests in 6. that models like the ones from Graves et al. could be significantly better at NLU.

External memories are an aspect which is investigated in the work of Graves et al., and can be also viewed under a Cognitive Science perspective, considering the work by McClelland and other contributions about the role of the hyppocampal memory.

Kanerva's [Sparse Distributed Memory](https://en.wikipedia.org/wiki/Sparse_distributed_memory) model of human memory inspired the work in 4. by Wu et al. (continuing the work of Alex Graves and in collaboration with Lillicrap). 

==What can be the connections between properties offered by a CLT-based system (with external memory) and the ability to develop symbolic behaviour?== (see 2., 3. and 6.)
- 6 mainly investigates the possibilities opened in the area of NLU. One of McClelland's main theses is that true understanding of language and skill in language manipulation requires the understanding (or *modeling*) of a context. This feature is given at an embrional level by transformers, thanks to the attentional mechanism, and by BERT which extends the attentional ability to the future, but is fully exploited in CLS theory-based systems.
- 6 also highlights the role of embodiedness of experience as a crucial aspect of symbolic (specifically, linguistic) behaviour. 

---
1. Graves et al., Hybrid computing using a neural network with dynamic external memory [Hybrid computing using a neural network with dynamic external memory](@graves_hybrid_2016.md)
2. Santoro et al., Symbolic behaviour in Artificial Intelligence [Symbolic Behaviour in Artificial Intelligence](@santoro_symbolic_2021.md)
3. Kumaran et al., Complementary Learning Systems Theory Updated [@kumaran_what_2016](@kumaran_what_2016.md)
4. Wu et al., The Kanerva Machine: A Generative Distributed Memory
5. Botvnik et al., Deep RL & Neuroscientific Implications
6. McClelland, Placing Language Integrated Understanding System [embodiedness]
7. Chollet, Measure of Intelligence