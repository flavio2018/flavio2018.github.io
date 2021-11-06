# Neural Turing Machines
<p style= "text-align: right"><i>Created 26/10/2021</i></p>

## What can they do?
- store observations in memory and replay them[^olah]
- sort values in the memory [^olah]
- perform classic computations, such as parsing[^passen]
- be used to construct maps of an environment in the external memory[^zhang]

## What can't they do?
- ...

## What are the hard parts?
- many epochs of training, lots of data
- they are hard to train due to sequential nature and their depth when unfolded[^kaiser]

[^olah]: [[@olah_attention_2016|Attention and Augmented Recurrent Neural Networks]]
[^passen]: [[@paassen_stack_2021|Reservoir stack machines]]
[^kaiser]: [[@kaiser_neural_2016|Neural GPUs Learn Algorithms]]
[^zhang]: [[@zhang_neural_2020|Neural SLAM: Learning to Explore with External Memory]]