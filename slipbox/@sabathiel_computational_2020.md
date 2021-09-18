---
title: A Computational Model of Learning to Count in a Multimodal, Interactive Environment
authors: Silvester Sabathiel, James L McClelland, Trygve Solstad
year: 2020

---

A Computational Model of Learning to Count
---

-   _p.2_ The authors designed a model which can learn to perform several number-related tasks, on the basis of the assumption that a number sense is learned by interaction with the environment in different ways. Also, they aim to create evidence of learning of a more general “number sense”, rather than a specific number-related task.
    
-   _p.2_ The agent model is trained in a virtual environment including visual perception of a 4x4 grid, a virtual hand, a virtual utterance mechanism, and guidance commands and feedbacks. Hence, the model learns by backpropagation, and not by learning to maximise rewards (Reinforcement Learning).
    
-   _p.2_ The tasks the model was trained on are: count-all-objects, count-all-events, recite-N, give-N.
    
-   _p.3_ The model includes a component processing visuo-spatial signal (Conv-LSTM) and another one to process language (commands and model utterance) (LSTM). Two fully connected layers produce the motor and verbal outputs, respectively.
    
-   _p.4_ The model reached perfect, statistically significant performance on count-all-events and give-N tasks. Somewhat worse performance was reached on the other tasks.
    
-   _p.4_ The model was trained to learn all four tasks using interleaved learning; nearly perfect performance was reached in all tasks, except count-all-objects task which wasn’t learned properly.
    
-   _p.4_ Notice that the count-all-task is the hardest to learn for this model, since it requires to integrate visual information processing with utterance production and hand movement (touching), in correspondance one with the other.
    
-   _p.4_ The authors were able to reach perfect performance for all tasks, as well as for transfer learning, adopting regularization techniques (dropout) and modifying the network architecture and learning algorithm.
    
-   _p.5_ For tasks requiring to learn to associate number words to elements of the environment (either objects or events) (all but recite-N), three common learning stages were observed. At first, the network learned to output the same number word for each timestep; then, it learned to utter the number-word at the same time of counting objects in the scene or of occurring of events; finally, the network learns to utter number words in the correct order, starting from the smallest ones (for which it receives more practice).
    
-   _p.5_ Pre-training the network on the recite-N and touch-all-objects-once tasks resulted in a considerable performance improvement in the count-all-objects task.
    
-   _p.6_ A visual memory mechanism consisting in “mentally tagging” touched objects was found to emerge in one of the long-term memory cells of the Conv-LSTM net.
    
-   _p.7_ Further reasearch efforts identified by the authors are: extending to numbers beyond nine (grouping by ten), integrating approximate quantity estimation (ANS) and enriching the linguistic context of the agent.

---

The model from Sabathiel, McClelland and Solstad adopts a developemental approach in attempting to model the process of learning exact numerosity.  
  
Some important facts about the model are:  
- it is an agent model  
- it is multimodal  
- it can learn four different tasks  
- reciting the number line and touching all objects in a scene helps learning the other tasks  
- a visual, mental representation of counting in time emerges in the model.  
  
These points relate to the possibility that the model actually reproduces a sense for exact numbers, rather than one specific numerical task.