## The role of external representations when learning to count

---
## The single agent model
![Sketch model](sketch_model_v3.png)

---
## Model training
- Deep Q-Learning
	- Softmax action selection
	- Replay memory
	- Policy & Target Networks
- Curriculum Learning
---

## Reward definition
- Label-based
	- (optional) punishment for wrong label
- Simple curiosity mechanism
---

## Training monitoring
![training_monitoring_tensorboard.png](training_monitoring_tensorboard.png.md)

---

## Visualization of agent's behaviour
![model_implementation_v1.png](model_implementation_v1.png.md)

---
## Systematic testing
| n. obj. | accuracy | 
|-|-|
| 1 | 0.000| 
| 2 | 0.988| 
| 3 | 0.240| 
| 4 | 0.000|

---

## Preliminary results
- Agent does not learn to correctly classify numerosity
	- possibly, due to sparsity of rewards