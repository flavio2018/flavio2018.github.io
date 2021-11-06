<p style= "text-align: right"><i>Created 02/11/2021</i></p>

Today I reorganized (cannot really say refactored yet, since I don't have any test implemented) the part of the CMV codebase that is related to the building of the classifier inputs, labels and masks.

It was a long process - longer than I expected - lasting from about 11 in the morning until nearly 6 in the afternoon, with a lunch break of approximately two hours. Overall, it has been full five hours of work.

I particularly enjoyed a couple of moments in the process, when I gained some insights about the code I had already written which guided me in the reorganization process.

The first moment is when I realized I didn't need to have a general builder for the classifier input, but rather two separate functions that created two specific kinds of inputs, more closely mirroring the research domain. This was a clear example of YAGNI principle, since I had added a lot of unuseful flexibility that hid the true intent of the code, as the research domain is in the present moment.

The second moment is when I realized I could handle the building of the inputs in a different way, starting from a specific set of posts considered. Indeed, all I'm doing is giving as inputs different specific representations of a set of posts. Therefore, I have chosen to select that subset in advance and then extract the relevant information (profiles or tfidf representations) starting from that.