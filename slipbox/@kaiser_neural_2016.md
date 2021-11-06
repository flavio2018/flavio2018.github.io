---
title: Neural GPUs Learn Algorithms
aliases: ["Neural GPUs Learn Algorithms"]
authors: Łukasz Kaiser, Ilya Sutskever
year: 2016
abstract: Learning an algorithm from examples is a fundamental problem that has been widely studied. Recently it has been addressed using neural networks, in particular by Neural Turing Machines (NTMs). These are fully differentiable computers that use backpropagation to learn their own programming. Despite their appeal NTMs have a weakness that is caused by their sequential nature they are not parallel and are are hard to train due to their large depth when unfolded. We present a neural network architecture to address this problem the Neural GPU. It is based on a type of convolutional gated recurrent unit and, like the NTM, is computationally universal. Unlike the NTM, the Neural GPU is highly parallel which makes it easier to train and efficient to run. An essential property of algorithms is their ability to handle inputs of arbitrary size. We show that the Neural GPU can be trained on short instances of an algorithmic task and successfully generalize to long instances. We verified it on a number of tasks including long addition and long multiplication of numbers represented in binary. We train the Neural GPU on numbers with up to 20 bits and observe no errors whatsoever while testing it, even on much longer numbers. To achieve these results we introduce a technique for training deep recurrent networks parameter sharing relaxation. We also found a small amount of dropout and gradient noise to have a large positive effect on learning and generalization.
---
# Neural GPUs Learn Algorithms

<p style="text-align: right">
<a href="
http://arxiv.org/abs/1511.08228
">
<i>
Łukasz Kaiser, Ilya Sutskever, 2016</i>
</a>
</p>

***
[code](https://github.com/openai/neural-gpu)
[video](https://www.youtube.com/watch?v=LzC8NkTZAF4)

A research by Google where the authors present a model that they claim to be easier to train than NTM.

Main topic: making the NTM parallel.

Main claims: 
- presentation of a new architecture, based on a convolutional gated recurrent unit (CGRU)
- this architecture is easier and faster to train than NTM
- Neural GPU can be trained to multiply short binary numbers and be able to multiply long binary numbers with no error
- presentation of a training algorithm ("parameter sharing relaxation")
- a small amount of dropout and gradient noise have a positive effect on generalization

---

Sequence-to-sequence LSTM networks are fantastic on a number of tasks, but they fail on simple algorithmic tasks on long sequences. In principle, NTM can solve these tasks but they are hard to train because they are deep and learn a sequential program. The neural GPU in contrast is designed to be shallow and parallel.

The Neural GPU is composed of a variation of a Gated Recurrent Units (GRU).

The architecture and the way it process inputs are different from the NTM. All the inputs are stacked together in a matrix, and the matrix is manipulated over time by several CGRU cells (as if it were an external representation).

The matrix representation of numbers presented as binary inputs is the concatenations of the inputs "folded" in a three dimensional matrix (also a two dimensional matrix is possible but using with is more efficient, see *Why use width?* in sec. 4 in the paper).

An intuition on why the model works might be that it learns the regularity of the operations thanks to its convolutional structure. However, I can't fully explain this for multiplication ([how does binary multiplication work?](http://www.binarymath.info/binary-multiplication.php)).

An interesting thing is that the model doesn't work with decimal representation.