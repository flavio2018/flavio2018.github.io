---
title: Neurosymbolic AI The 3rd Wave
aliases: ["Neurosymbolic AI: The 3rd Wave"]
authors: Artur d'Avila Garcez, Luis C. Lamb
year: 2020
abstract: Current advances in Artificial Intelligence (AI) and Machine Learning (ML) have achieved unprecedented impact across research communities and industry. Nevertheless, concerns about trust, safety, interpretability and accountability of AI were raised by influential thinkers. Many have identified the need for well-founded knowledge representation and reasoning to be integrated with deep learning and for sound explainability. Neural-symbolic computing has been an active area of research for many years seeking to bring together robust learning in neural networks with reasoning and explainability via symbolic representations for network models. In this paper, we relate recent and early research results in neurosymbolic AI with the objective of identifying the key ingredients of the next wave of AI systems. We focus on research that integrates in a principled way neural network-based learning with symbolic knowledge representation and logical reasoning. The insights provided by 20 years of neural-symbolic computing are shown to shed new light onto the increasingly prominent role of trust, safety, interpretability and accountability of AI. We also identify promising directions and challenges for the next decade of AI research from the perspective of neural-symbolic systems.
---
# Neurosymbolic AI: The 3rd Wave
<p style="text-align: right"><i>arXiv:2012.05876 [cs], 2020</i></p>

*Artur d'Avila Garcez, Luis C. Lamb*

[Resource on the Web](http://arxiv.org/abs/2012.05876)

---
The paper has some interesting insight at the crossing-point between symbolic reasoning in artificial intelligence and explainability, looking at the next ten years goals of the AI community. The authors have a perspective and language which is possibly closer to GOFAI (e.g. first and second order logic reference), but they see them from the perspective of searching reconciliation with DL. 
- p.8 In general, they offer a reconciling perspective with GOFAI, aiming at reconsidering their tools in the context of symbolic DL ("neurosymbolic AI"). This approach is perhaps in contrast with the one of [Symbolic Behaviour in Artificial Intelligence](@santoro_symbolic_2021.md).
- p.16 Here the authors mention that the efficacy of "distributed approximate reasoning" of Differentiable Neural Computer-like models ([[reference/papers/@graves_hybrid_2016]]) is limited. They see the external memory of DNCs as a symbolic system for reasoning, which the neural core interacts with. The reasoning is seen as "approximate" because representations are not discrete and are learned. 
- p.18 Two main areas of application of "neurosymbolic AI" are NLU ([@mcclelland_placing_2020](@mcclelland_placing_2020.md)) and planning.
- p.24 Daniel #Kahneman pointed out that a further layer of system 2 reasoning is needed in DL systems.