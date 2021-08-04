# Programming principles
I'm looking for some coding principles/heuristics/rules of thumb to follow to try and write more maintainable code. There are surely many resources that will help doing that; I'll collect here useful principles I find to remember and reflect upon them.

References:
- https://www.makeuseof.com/tag/basic-programming-principles/
- https://www.geeksforgeeks.org/7-common-programming-principles-that-every-developer-must-follow/

---

## DRY
Don't repeat yourself. It's the same principle that drives the refactoring of Jupyter Notebooks[^jupyter]. Incapsulating code in a function, avoid copy-pasting and repeated lines of code with the same structure: these are examples of the DRY principle in practice.

## Open/closed
Code should be *open to extension and closed to modification*. In other words, try to write code that lasts. Try to foresee what could be some points where code might need to be modified in the future and design it so that modifications can be implemented as extensions of your existing code, rather than direct modification that will possibly break stuff.

# OOP principles
Some principles have at least been invented (I guess!) in the context of OOP, and they also make more sense within it.

## Single Responsibility Principle
Each module or class should have only one responsibility. Or, it should have only one reason to change. Or, it should not be cluttered with lots of additional behaviors as development goes by; rather, it should be refactored so that new classes are responsible for new behaviors, as they become more complex.

[*aside note*] The force that pushes to refactor code, following the SRP as much as others, is a positive force that makes us *rethink* about the code, about its structure, its design and the way it works and it's done. It's actually the best part of programming, the one where it gets creative and interesting rather than repetitive and frustrating. Also, one does not have to deal with something new and unexpected (such as hunting for a bug or figuring out how a library works). Instead, one can finally work with his/her own code (which one should know pretty well) and giving as granted the fact that it works, one can work to make it work and appear (form *is* substance) even better. 

[^jupyter]: [38_jupyter_notebooks_best_practices](38_jupyter_notebooks_best_practices.md)