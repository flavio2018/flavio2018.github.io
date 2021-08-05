---
title: Deep Learning for Symbolic Mathematics
authors: Guillaume Lample, François Charton
year: 2019
---

Deep Learning for Symbolic Mathematics
---

-   _p.1_ Key idea: model methematical expressions and problems using them (integration, ODEs) as a NLP task using seq2seq models
    
-   _p.2_ Key representation idea: expressions as trees
    
-   Main results: 
    
    -   _p.9_ integration works very well; solving ODEs works quite well
        
    -   _p.10_ the model is able to find solutions with different yet equivalent algebraic form
        
    -   _p.10_ the model trained on dataset preferring very right- or left-skewed trees is unable to generalize on the other kind
  
---

The model in Lample, Charton (2019) shows that the strong syntactic structure which is typical of algebraic expressions can be successfully modeled with an encoder-decoder architecture, provided with suitable sequential representation of expressions.  
  
However, as the lack of generalization ability also prove, the modle only learns a shallow logic to manipulate expressions (and the corresponding problems), based on the syntax of the representation of mathematical concepts, rather than actually learning their mathematical "meaning" once and for all.