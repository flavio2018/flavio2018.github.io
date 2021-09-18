---
title: An Opinionated Guide to ML Research
aliases: ["An Opinionated Guide to ML Research"]
authors: John Schulman
year: 
abstract: 
tags: ["#h/science/doing-research"]
---
# An Opinionated Guide to ML Research

<p style="text-align: right">
<a href="
http://joschu.net/blog/opinionated-guide-ml-research.html
">
<i>John Schulman's Blog - 2020</i>
</a>
</p>

*John Schulman*
***

- The essay covers three topics that are, according to the author, the key to doing effective research: working on the right problems, making continual improvements and achieving personal growth (as a scientist).

## Choosing the research topics
The author has some suggestions about getting better at finding the right topic to work on - how to build that *taste* that also Andrej Karpathy talks about[^karpathy]. His suggestions are: 
- read and, most importantly, discuss papers with other experienced people in the field.
- work with other researchers in similar areas as yours, so that you learn from their experience and not only yours. 
- talk about research topics with experienced researchers, trying to take their suggestions about what is worth working on.
- finally, think about what ideas survive the passing of time, when is theory useful, when is experimental evidence transferable (i.e. not related to just the specific experimental setting in which it was found, but is likely to be something more general), what research lines and trends are more likely to survive others and change the field in the following years.
- > *As empirical evidence for the importance of 1-3, consider how the biggests bursts of impactful work tend to be tightly clustered in a small number of research groups and institutions. That’s not because these people are dramatically smarter than everyone else, it’s because they have a higher density of expertise and perspective, which puts them a little ahead of the rest of the community, and thus they dominate in generating new results.*
- Schulman argues you can choose your next research project in two ways: 
	- starting from a practical idea that you have e.g. reading a paper, about how to something might practically be done. This is somehow a very greedy approach, a little myopic, and at worst it might end-up in doing the kind of incremental research that Karpathy warns about.
	- starting from a general goal you want to achieve in your field and then try to formulate problems that bring closer and closer to that goal. Finding the general goal is not straightforward, though: it's connected with the "taste" for good topics one should strive to build and it is itself a "vision" one should develop over time.
- > *One major downside of idea-driven research is that there’s a high risk of getting scooped or duplicating the work of others. Researchers around the world are reading the same literature, which leads them to similar ideas. ... On the other hand, with goal-driven research, your goal will give you a perspective that’s differentiated from the rest of the community. It will lead you to ask questions that no one else is asking, enabling you to make larger leaps of progress.*
- From a psychological perspective, being in the position where you work for a bigger goal makes the ups and downs of research more bearable. Also, attacking this kind of broader goal can be done more easily in teams, where everyone brings a different perspective, whereas more technical work on single practical ideas can be mostly done alone or in pairs.
- As an example, policy gradient methods (TRPO, GAE, PPO) were developed by Schulman in his PhD as the result of the goal of applying reinforcement learning to the problem of 3D humanoid locomotion.
- One thing one should try to do is not solving the chosen problem in ways that are too specific to the domain at hand, but striving for generality, to develop ideas that can be applied also to other areas of research.
- Finally, one should choose an ambitious goal (with an attack). One should ask him/herself: can the project I am working on lead to a potential 10x improvement in the field? Or, in general, what's the best possible expected improvement? One should be aware that incremental work (the kind of work that solves minor issues, makes small adjustments to achieve 10% or x% of improvement on something) should not be the main, general focus of one's work. The incremental work will be there to be done anyway, but it should lead to something bigger and more important.

## Making improvements
- Schulman suggests to keep a journal of ideas and experimental results mixed up, that serves both to keep track of the work done, to review one's ideas after having them and writing them down on-the-spot, to keep track of experimental results. Also, and importantly, he suggests to make reviews of one's notes once every 1-2 weeks.
	- Having discovered the slip-box, I personally think that the 	usefulness of writing down one's ideas is undoubtable. However, I would probably keep the different things he talks about in different places in the slip-box (e.g. I already have a place for ideas that come to me thanks to literature or other sources). Something I don't do is recording the experiments I run - but that's because I don't run so many outside of specific projects. However, in that context I started some form of recording that I could certainly improve. 
	Something I cannot do as easily with my current method is doing weekly reviews. However I can find a way to do that and I definitely should to some form of review of what I write.

- The general piece of advice by Schulman on how long one should stay on a project is to be more conservative than liberal when deciding whether to switch. In particular, in perspective one should see that the time spent on projects in the previous months has mostly led to deliverable results (e.g. papers or blog posts) and a small portion of time was dedicated to dead-end projects.

## Complementary learning
- Schulman argues that in order not to acquire knowledge only in the field that is necessary for your main research, one should continue studying also from other sources. He indicates three main kinds of resources, with different advantages:
- textbooks: they provide a compendium of knowledge in a discipline that is much more condensed than in papers. One can quickly learn new ideas from there and become aware of techniques and concepts previously unknown.
- PhD thesis from notable and interesting researchers in one's field: from these one can mainly get an interesting view of the past and the future of the field when the thesis was written. The most recent ones are more interesting, but also the older ones can be useful.
- papers (both main and minor ones): the main papers should be read and their methods and results should be reproduced, if possible. One good thing about this is that they provide a faster feedback loop than new research ideas, since the expected outcome is known. Then, it should be easier to do independent research. An example of main papers that should be reproduced are: Attention mechanisms, BERT, Differentiable Neural Computers, etc. One could even start from older stuff like LeNet, RBMs, etc.
Keeping an eye on minor papers could give an idea of what are the most fast-spreading techniques in the field which might be worth trying.

[^karpathy]: [[@karpathy_survival_2016|A Survival Guide to a PhD]]