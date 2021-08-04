Hybrid computing using a neural network with dynamic external memory
---
- p.1 The work presents a medel called Differentiable Neural Computer which consists of a neural network that learns to use an external memory to solve complex tasks. It can be trained either with Reinforcement Learning or with Supervised Learning algorithms. It can effectively solve question-answering tasks, reasoning on graphs and blocks puzzles.
- p.1 The goal of the system is to overcome the limitation of DNN in which memory and computation coincide, in the form of connection weights. This is also motivated by studies in cognitive science and psychology about the role of the hyppocampus and its interaction with the prefrontal cortex in reasoning processes.
- p.1 The weightings vector used to select the row(s) to be read or written in the memory is created using a differentiable attention mechanism called *content lookup*. This simply consists in comparing a *key vector* output by the controller network to every vector in memory. 
- p.2 The model uses attention also to keep track of the order in which positions in memory were written. To do so, it learns to write an $N·N$ matrix (where N is the number of rows in the external memory) in which the element in position $i,j$ is close to 1 if the i-th location was written consequently to j-th. This is reflected in a modification to the *key vector* via matrix-vector multiplication in which the positions written immediately after (or before, depending on whether left-side or right-side multiplication is used) the most active positions in the key vector are emphasized.
- p.2 Finally, the model uses attention to decide which locations to write. The architecture includes a vector of values in [0,1] which signal whether a position was used or not in the memory. The values can be increased when they memory is written as well as decreased when the memory is read (freeing memory). 
- p.2 The model is trained on three tasks: synthetic question answering, reasoning on graphs and a block puzzle problem. On the first task, the network was presented short pieces of text in which some situation was presented; then, it needed to answer a question which required to take into account relationships explicited in the text and filtering confounding information.
- p.3 The second task the model is trained to solve is a set of task on graphs or trees. They comprehend traversal (output the final node after traversing a sequence of edges), finding the shortest path between two nodes, and inference (given labels representing relationships between nodes in a tree, output the node corresponding to that degree of relationship wrt a node given as input).

---

The network is built in such a way to be differentiable. The idea of differentiable systems is widely used to design models which can learn but are structured as the designer pleases (as long as he or she can make the model differentiable).

The metaphore of CPU and RAM, paralleling Von-Neumann architectures, is repeatedly used throughout the paper. As a matter of fact, the two contexts are only partially similar. 
- The external memory of DNCs is a matrix of arbitrary real values, not only 0/1. 
- The coding used in the memory is *learned* by the controller network, and not specified a priori. 
- The memory values can be jointly read and written, according to the weightings vector.
Thus, I suppose that the representational capacity of the external memory of a DNC is higher than that of an equally-sized RAM.

 The key finding in the paper is that the external memory enables planning and structured reasoning tasks in the model. 
 ==How does this relate to cognitive-neuroscience observations and findings about the role of the hyppocampus?==
 
 Judging from the graph reasoning task, we can say that the network is particularly good at representing structured knowledge (of graph form) in memory. This can be extended, to some extent, to the first task, in which textual information can be represented also in a noun-predicate-noun graphical form, hence the network could have learnt to memorize the association between pairs of words and then retrieve the relevant ones to answer the questions.
 
 This does not mean that the network actually models words' *meanings*. It is questionable to what extent this is a reasonable model of human reasoning on similar tasks requiring to understand relationships between entities.
 
 Can this kind of model favor interpretability? They cannot intrinsically improve interpretability in tasks where DL models have been used until now (object detection, translation, etc.), simply because they would not be exploited to solve such tasks. It is equally important, however, to develop explainable algorithms which deal with structured knowledge and are capable to solve question answering or graph reasoning tasks. Is it possible to use external memories to develop intrinsically explainable algorithms which solve these tasks? It depends on the degree of interpretability of the external memory. If we can design external memories whose usage by the model can be interpreted (more than we can interpret past DNN's internal states), then this could be possible.