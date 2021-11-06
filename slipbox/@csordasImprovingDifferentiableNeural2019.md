---
title: Improving Differentiable Neural Computers Through Memory Masking, De-Allocation, and Link Distribution Sharpness Control
aliases: ["Improving Differentiable Neural Computers Through Memory Masking, De-Allocation, and Link Distribution Sharpness Control"]
authors: Róbert Csordás, Jürgen Schmidhuber
year: 2019
abstract: The Differentiable Neural Computer (DNC) can learn algorithmic and question answering tasks. An analysis of its internal activation patterns reveals three problems Most importantly, the lack of key-value separation makes the address distribution resulting from content-based look-up noisy and flat, since the value influences the score calculation, although only the key should. Second, DNC's de-allocation of memory results in aliasing, which is a problem for content-based look-up. Thirdly, chaining memory reads with the temporal linkage matrix exponentially degrades the quality of the address distribution. Our proposed fixes of these problems yield improved performance on arithmetic tasks, and also improve the mean error rate on the bAbI question answering dataset by 43%.
---
# Improving Differentiable Neural Computers Through Memory Masking, De-Allocation, and Link Distribution Sharpness Control

<p style="text-align: right">
<a href="
http://arxiv.org/abs/1904.10278
">
<i>
Róbert Csordás, Jürgen Schmidhuber, 2019</i>
</a>
</p>

***