# Propensity score matching
[On Wikipedia](https://en.wikipedia.org/wiki/Propensity_score_matching)
[In Python Causality Handbook](https://matheusfacure.github.io/python-causality-handbook/11-Propensity-Score.html)

PSM is a statistical technique used to control the effect of confounders in observational studies. While in randomized experiments the effect of possible confounders on the observed variable can be taken into account, creating randomized treatment and control groups, this is clearly not possible in observational studies.

PSM is a specific case of the more general technique of [matching](https://en.wikipedia.org/wiki/Matching_(statistics)), that consists in pairing elements of the treatment group to ones in the control group that have similar values of confounding variables, so to only take into account the effect of the treatment and avoid confounding.

The procedure of PSM consists in the following phases:

0. Assume to have a dataset including both the treated and untreated examples; identify the possible confounders (in our case, activity on one's own subreddit, activity on sociopolitical subreddits, time in which the post was written, to control for the density of the profiles).
1. Fit a logistic regression model that predicts $P(T=1|C=c)$, i.e. the probability that the sample belongs to the treatment set given its values of the confounders $c$. Transform the probabilities obtained for each sample in logits; these will be called *propensity scores*.
2. Pair each sample of the treatment with one in the control group that has a "similar" value of the propensity score; the similarity can be established using an algorithm such as [KNN](46_befd_KNN).
3. Build new treatment and control groups that contain only matched samples (in case of unbalanced treatment and control, we can have elements in the majority group assigned to elements in the minority group more than once).
4. Finally, we should assess whether the confounders have similar distributions in the paired treatment and control groups. 

This topic is strictly related on the whole field of study about causality, of which [@pearl_causality_2000](@pearl_causality_2000.md) probably the best introduction.