---
title: Understanding the difﬁculty of training deep feedforward neural networks
aliases: ["Understanding the difﬁculty of training deep feedforward neural networks"]
authors: Xavier Glorot, Yoshua Bengio
year: 2010
abstract: Whereas before 2006 it appears that deep multilayer neural networks were not successfully trained, since then several algorithms have been shown to successfully train them, with experimental results showing the superiority of deeper vs less deep architectures. All these experimental results were obtained with new initialization or training mechanisms. Our objective here is to understand better why standard gradient descent from random initialization is doing so poorly with deep neural networks, to better understand these recent relative successes and help design better algorithms in the future. We ﬁrst observe the inﬂuence of the non-linear activations functions. We ﬁnd that the logistic sigmoid activation is unsuited for deep networks with random initialization because of its mean value, which can drive especially the top hidden layer into saturation. Surprisingly, we ﬁnd that saturated units can move out of saturation by themselves, albeit slowly, and explaining the plateaus sometimes seen when training neural networks. We ﬁnd that a new non-linearity that saturates less can often be beneﬁcial. Finally, we study how activations and gradients vary across layers and during training, with the idea that training may be more difﬁcult when the singular values of the Jacobian associated with each layer are far from 1. Based on these considerations, we propose a new initialization scheme that brings substantially faster convergence.
---
# Understanding the difﬁculty of training deep feedforward neural networks
<p style="text-align: right"><i>Proceedings of the Thirteenth International Conference on Artificial Intelligence and Statistics, 2010</i></p>

*Xavier Glorot, Yoshua Bengio*

[Resource on the Web]()

---