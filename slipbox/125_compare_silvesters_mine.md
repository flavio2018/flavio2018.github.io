# Comparison of Silverser's runs with mine
<p style= "text-align: right"><i>Created 13/08/2021</i></p>

In parallel with the attempt of having some interesting results coming from rewarding the agent for using the external representation[^diary], I can try and get something that can be written in the thesis by comparing my original experiments[^runs] with the ones done by Silvester.

I have (more or less) been able to obtain convergence of the MLP agent for up to 5 objects (I don't have classification accuracy data). The convergence happened without the agent using the external representation. The first thing I am trying to test is whether
- the learning is more rapid if I use a reward of greater magnitude.

Up to now, it doesn't seem so. 

Then, what I would like to say ideally is that an agent that is presented the numerosity temporally uses the external representation, while mine does not. There are currently two known issues that make this comparison difficult:
- Silvester used a CNN while I used an MLP;
- Silvester rewarded the agent for using the ext. rep. while I did not, in the original setting.

What I should do, in order, is:
1. obtain a converging result from Silvester's setting;
2. try and use a CNN in my setting.

***

The current reward used by Silvester in the setting with temporally presented inputs is:
- if after an event the agent writes, give small reward
- else, give small punishment
- if after any timestep that does not contain an event the finger was moved, give small reward
- else, give small punishment
- if it's the last timestep and the agent gave the right answer, give small reward

[^diary]: [117_mt_experiments_diary](117_mt_experiments_diary.md)
[^runs]: [118_mt_runs_results](118_mt_runs_results.md)