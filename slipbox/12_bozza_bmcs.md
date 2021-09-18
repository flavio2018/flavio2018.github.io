Explainable high-level cognitive abilities in Memory Augmented Neural Networks
---

Background
---
%%*Background of your work based on an updated state of the art in the domain of your research project.*
- Advances in Deep Learning and Artificial Intelligence aiming at exploring the possibilities of symbolic reasoning in Deep Learning models. Reconciling (?) classic GOFAI techniques with the latest and most effective (in the perceptual domain) ANN-based algorithms (Santoro et al. 2020, Garcez et al. 2020).
- The global interest in explainability of AI algorithms based on DL (XAI) in order to guarantee the safety and reliability in usage for social, economical and political purposes.
- Reference to modern architectures, external memories, attention (transformers).%%

In the latest two decades, Deep Learning algorithms have been widely applied to solve tasks ranging from NLP [Brown et al., 2020, Devlin et al., 2020], to playing board games[^silver] (Silver et al.), to speech recognition [] and object detection [Tan et al., 2020], thanks to their effectiveness in these domains which was unprecedented in the history of Artificial Intelligence. Deep Learning algorithms, loosely modeling the neurobiological functioning of animal brains, are particularly good at dealing perceptual data (raw images, audio or even text), from which they are able extract statistical information, which is efficiently encoded by the networks in the so-called hidden layers (a capacity called representation learning).

However, Deep Learning models are way less effective at other traditional tasks in the domain of Artificial Intelligence, such as reasoning, planning, and dealing with structured knowledge in general. These abilities are considered the peak of human intelligence, and for decades the research effort of the Artificial Intelligence community has focused on creating algorithms which could mimic human performance in activities falling in these areas. After nearly twenty years of attention focused on Deep Learning algorithms, the Artificial Intelligence community is now looking back at the tradition in the field to try and approach the problem of developing Deep Learning algorithms which are capable of higher levels forms of intelligence[^bengio] (Santoro et al. 2020, Garcez et al. 2020, Marcus, 2020).

This is also motivated by the fact that the wide application of Deep Learning models had an important impact on society, and is expected to have an even greater one in the future. The European Commission recently published a regulation on the use of AI on European grounds for any public or private subject. There is, therefore, increasing need to develop explainable Artificial Intelligence algorithms, whose internal functioning can be understood by the human user who is finally to judge the reliability of the result.

Project overall goal
---
%%- Explore the possibilities of emergence of symbolic reasoning in Deep Learning architectures using external memories
- Explore XAI techniques based on cognitive science concepts%%

The first goal of this project is to explore the possibilities of designing Deep Learning models which are able to deal with higher-level forms of knowledge, including symbols, and therefore to show a degree of high level cognitive abilities. Attention mechanisms [Vaswani et al., 2017] will be key features of the architectures that will be tested, since they are now considered a standard way to solve long-term dependencies problems in networks dealing with sequential data. Furthermore, based on insights from cognitive science and recent trends in the Deep Learning community, the project's goal is to explore how Memory Augmented Neural Network (MANN) models can be exploited to deal with abstract forms of knowledge [Graves et al., 2016, Wu et al., 2018]. External memories, which can be endowed with attentional mechanisms themselves, can be used in a flexible way from a core module of the network which can learn to use the memory to solve its tasks. In particular, it has been shown that using such memories can improve the performance of neural networks models on tasks requiring forms of reasoning and planning.

The second goal of the project is to develop new models and evaluation techniques which enable the development of intrinsically explainable Artificial Intelligence algorithms, based on the ideas in cognitive science which these models are inspired by. For example, developing techniques which enable the interpretation of external memory usage could allow to explain the "reasoning process" that a network follows to produce a given output. This perspective is encouraged by the fact that in [Graves et al., 2016] it was shown that matrix-like external memories are accessed according to a logic which mimics the structure of training data and therefore can be interpreted to some extent.

Expected advances to the discipline
---
%%- Explore the impact of external memories on reasoning abilities of Deep Learning systems
- Mathematical learning as a case study in cognitive science and cognitive modeling
- new forms of memories? %%

Memory Augmented Neural Networks have been developed for several years, showing impressive performance in tasks such as question answering, reasoning on graphs and blocks world games in which tasks were communicated symbolically [Graves et al., 2016]. However, up to now the models have only been tested on simple benchmarking tasks, and a version optimized to reduce training time has been tested on question answering and text comprehension tasks, showing reasonably good performance when compared to task-specific fine tuned models [Franke et al., 2018]. Exploring the extent to which the high-level reasoning abilities of models using external memories are preserved when dealing with real-world data is a key step to further investigate the applicability of these models. For example, MANN models could be tested on more realistic question answering tasks than the bAbI tasks, which would require the model to extract information about relationships between entities from a more natural setting.

Another research area which can represent an important use case for MANNs is learning of mathematical concepts [Testolin, 2020]. Indeed, reasoning using mathematical concepts is a scenario in which modeling relationships between entities is a key capability in order to solve proposed problems. For example, in the domain of arithmetic, abstracting from the variability of individual problems to effectively model the rules that describe arithmetical operations could be facilitated by the possibility to use an external memory.

Expected impact or outcomes
---
%%- Inherently explainable MANN models based on cognitive science concepts
- Novel metrics to evaluate the explainability of DL algorithms
- What models, applied on what domains and tested with what metrics?
	- Symbolic tasks? Besides manipulation and learning of concepts of exact numerosity%%

The main expected impact of the project is to gain deeper understanding of the applicability of MANN models to real-world scenarios. The possibility to scale this kind of models to more natural data will likely require both mathematical and computational adjustments and new model design choices in order to make the models adaptable to new kinds and proportions of data.

At the same time, constant attention will be devoted to the interpretability of the designed models, designing ad-hoc model inspection techniques which will make the functioning of the designed models natively explainable, coherently with the priorities defined by current policies on AI at the European level.

Research plan
---
%%*Main phases of the planned work, expected duration, dependence relation between phases.*%%

Interdisciplinary aspects of the project
---
%%- Cognitive Science and Cognitive Psychology inform the structure of external memories based on the role of the hippocampus in human reasoning processes
- Artificial Intelligence and Computer Science give the technical means to design new explainable DL models, as well as the formal instruments to evaluate algorithms based on their explainability%%

One of the main problems that cognitive agents need to face when dealing with complex environments is the need to learn both the stable relationships or features of an environment, and the varying features of individual entities. Attempting to solve both problems with a single architecture leads to the so-called *catastrophic forgetting* problem, namely the inability of the artificial neural network to retain fundamental knowledge which it has already acquired when presented with new instances of training data. This is precisely the problem that MANN try to solve, using the external memory as a storage for individual level features and modeling the stable dynamics of the environment in the core module of the network.

Memory Augmented Neural Networks are considered to be a promising way to create models which are able of more natural interaction with symbolic systems, up to the paramount goal of a system capable of fully-developed natural language understanding, with performances comparable to human ones [McClelland et al., 2020]. This is also motivated by the similarity between the performances of such systems and the dynamics of interactions between hippocampus and neocortex in human mnemonic processes  involving different "kinds of memory", including episodic and semantic memory.

The Complementary Learning Systems theory is the cognitive psychology framework in which MANN can be placed. The theory has been recently reviewed by prominent cognitive neuroscientists [Kumaran et al., 2016], in light of new evidence from neuroscience experiments supporting the theory. In the article, the authors also highlight the relevant connections with engineering systems that try to emulate human cognition following a connectionist approach.

References
---
1. Brown, Tom B., Benjamin Mann, Nick Ryder, Melanie Subbiah, Jared Kaplan, Prafulla Dhariwal, Arvind Neelakantan, et al. «Language Models are Few-Shot Learners». _arXiv:2005.14165 \[cs\]_, 22 luglio 2020. [http://arxiv.org/abs/2005.14165](http://arxiv.org/abs/2005.14165).
2. Devlin, Jacob, Ming-Wei Chang, Kenton Lee, e Kristina Toutanova. «BERT: Pre-Training of Deep Bidirectional Transformers for Language Understanding». _ArXiv:1810.04805 \[Cs\]_, 24 maggio 2019. [http://arxiv.org/abs/1810.04805](http://arxiv.org/abs/1810.04805).
3. Silver, David, Julian Schrittwieser, Karen Simonyan, Ioannis Antonoglou, Aja Huang, Arthur Guez, Thomas Hubert, et al. «Mastering the Game of Go without Human Knowledge». _Nature_ 550, n. 7676 (ottobre 2017): 354–59. [https://doi.org/10.1038/nature24270](https://doi.org/10.1038/nature24270).
4. Tan, Mingxing, Ruoming Pang, e Quoc V. Le. «EfficientDet: Scalable and Efficient Object Detection». _ArXiv:1911.09070 \[Cs, Eess\]_, 27 luglio 2020. [http://arxiv.org/abs/1911.09070](http://arxiv.org/abs/1911.09070).
5. Santoro, Adam, Andrew Lampinen, Kory Mathewson, Timothy Lillicrap, e David Raposo. «Symbolic Behaviour in Artificial Intelligence». _arXiv:2102.03406 \[cs\]_, 5 febbraio 2021. [http://arxiv.org/abs/2102.03406](http://arxiv.org/abs/2102.03406).
6. Garcez, Artur d’Avila, e Luis C. Lamb. «Neurosymbolic AI: The 3rd Wave». _arXiv:2012.05876 \[cs\]_, 16 dicembre 2020. [http://arxiv.org/abs/2012.05876](http://arxiv.org/abs/2012.05876).
7. Marcus, Gary. «The Next Decade in AI: Four Steps Towards Robust Artificial Intelligence». _arXiv:2002.06177 \[cs\]_, 19 febbraio 2020. [http://arxiv.org/abs/2002.06177](http://arxiv.org/abs/2002.06177).
8. Vaswani, Ashish, Noam Shazeer, Niki Parmar, Jakob Uszkoreit, Llion Jones, Aidan N. Gomez, Lukasz Kaiser, e Illia Polosukhin. «Attention Is All You Need». _arXiv:1706.03762 \[cs\]_, 5 dicembre 2017. 
9. Graves, Alex, Greg Wayne, Malcolm Reynolds, Tim Harley, Ivo Danihelka, Agnieszka Grabska-Barwińska, Sergio Gómez Colmenarejo, et al. «Hybrid Computing Using a Neural Network with Dynamic External Memory». _Nature_ 538, n. 7626 (ottobre 2016): 471–76. [https://doi.org/10.1038/nature20101](https://doi.org/10.1038/nature20101).
10. Wu, Yan, Greg Wayne, Alex Graves, e Timothy Lillicrap. «The Kanerva Machine: A Generative Distributed Memory». _arXiv:1804.01756 \[cs, stat\]_, 18 giugno 2018. [http://arxiv.org/abs/1804.01756](http://arxiv.org/abs/1804.01756).[http://arxiv.org/abs/1706.03762](http://arxiv.org/abs/1706.03762).
11. Franke, Jörg, Jan Niehues, e Alex Waibel. «Robust and Scalable Differentiable Neural Computer for Question Answering». _arXiv:1807.02658 \[cs\]_, 7 luglio 2018. [http://arxiv.org/abs/1807.02658](http://arxiv.org/abs/1807.02658).
12. Testolin, Alberto. «The Challenge of Modeling the Acquisition of Mathematical Concepts». _Frontiers in Human Neuroscience_ 14 (20 marzo 2020): 100. [https://doi.org/10.3389/fnhum.2020.00100](https://doi.org/10.3389/fnhum.2020.00100).
13. McClelland, James L., Felix Hill, Maja Rudolph, Jason Baldridge, e Hinrich Schütze. «Placing Language in an Integrated Understanding System: Next Steps toward Human-Level Performance in Neural Language Models». _Proceedings of the National Academy of Sciences_ 117, n. 42 (20 ottobre 2020): 25966–74. [https://doi.org/10.1073/pnas.1910416117](https://doi.org/10.1073/pnas.1910416117).
14. Kumaran, Dharshan, Demis Hassabis, e James L. McClelland. «What Learning Systems Do Intelligent Agents Need? Complementary Learning Systems Theory Updated». _Trends in Cognitive Sciences_ 20, n. 7 (luglio 2016): 512–34. [https://doi.org/10.1016/j.tics.2016.05.004](https://doi.org/10.1016/j.tics.2016.05.004).

[^bengio]: [[@bengio_deep_2021]]
[^silver]: [[@silver_mastering_2017 1]]