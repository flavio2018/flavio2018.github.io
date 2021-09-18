---
title: Deep Learning for Symbolic Mathematics
aliases: ["Deep Learning for Symbolic Mathematics"]
authors: Guillaume Lample, François Charton
year: 2019
abstract: Neural networks have a reputation for being better at solving statistical or approximate problems than at performing calculations or working with symbolic data. In this paper, we show that they can be surprisingly good at more elaborated tasks in mathematics, such as symbolic integration and solving differential equations. We propose a syntax for representing mathematical problems, and methods for generating large datasets that can be used to train sequence-to-sequence models. We achieve results that outperform commercial Computer Algebra Systems such as Matlab or Mathematica.
tags: ["v/learning/deep"]
---
# Deep Learning for Symbolic Mathematics

<p style="text-align: right">
<a href="
http://arxiv.org/abs/1912.01412
">
<i>arXiv:1912.01412 [cs]
-
2019</i>
</a>
</p>

*Guillaume Lample, François Charton*
***

-   _p.1_ Key idea: model methematical expressions and problems using them (integration, ODEs) as a NLP task using seq2seq models
    
-   _p.2_ Key representation idea: expressions as trees
    
-   Main results: 
    
    -   _p.9_ integration works very well; solving ODEs works quite well
        
    -   _p.10_ the model is able to find solutions with different yet equivalent algebraic form
        
    -   _p.10_ the model trained on dataset preferring very right- or left-skewed trees is unable to generalize on the other kind
  
---

The model in Lample, Charton (2019) shows that the strong syntactic structure which is typical of algebraic expressions can be successfully modeled with an encoder-decoder architecture, provided with suitable sequential representation of expressions.  
  
However, as the lack of generalization ability also prove, the modle only learns a shallow logic to manipulate expressions (and the corresponding problems), based on the syntax of the representation of mathematical concepts, rather than actually learning their mathematical "meaning" once and for all.