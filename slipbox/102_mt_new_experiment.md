I currently have two working experiments:
1. the simple and not interesting SLP that classifies 1-sized squares
2. the well-known MLP that, almost obviously, classifies variable sized squares (not using the external representation)

I need at least one more experiment to make the results a bit more interesting. I think I have two roads:
1. accepting the fact that the agent does not use the external representation "because it doesn't need to". The right way to say this is that the experiment was badly designed. However, some interesting conclusions about modeling human behaviour with ANN could be made (hence the title of the thesis: "perceptual constraints...").
	1. This would probably require some form of comparison with other models (Silvester's MARL, Testolin's DBN, or both).
2. trying to force the agent to create an abstract representation, simulating the perceptual constraints that were not embedded in the model from the start (and whose role in my mind was implicitly played by the finger).
	1. in particular, I could try to force the agent to use the finger to point to the squares and to draw when they are touched, so that it learns a simpler representation for the squares than the one that is immediately available visually.
	2. the problem with this path is that learning the pointing-and-writing behaviour will likely need a lot of supervision, and thus the results would not be so meaningful.
	3. the finger can also be thought as the gaze of the agent. the agent could be given a small positive feedback when its gaze is on a square and an additional small positive reward when it makes a sign on the ext. rep. when the gaze is on a square.
	4. these supervised signals do not tell the agent 
		1. to point to all squares,
		2. to point to squares only once, and
		3. to draw only once per each square (squares have different shapes)
	5. hence, all these behaviors are still to be discovered by the agent and their discovery could possibly be interesting.
	6. an important point is that, for the agent to find it more convenient to build a symbolic ext. rep. instead of learning to associate the input pattern to the correct label thanks to the nonlinear approximation capacity, the environment should be complex enough (bigger than 4x4). however, this will lead to longer training time (bigger network and bigger space).

[102a_mt_architectural_costraints](102a_mt_architectural_costraints.md)