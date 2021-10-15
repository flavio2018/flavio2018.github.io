# Object orientation
What are the problems that object oriented programming is trying to solve? How else can they be dealt with?

One view that can unify the functional and object oriented paradigms is that focusing on *context*. Object orientation has as one of its main goals that of giving each *class* or *object* it's own state (or a shared state between instances, in the case of classes).

On the other hand, basing one's programming primarily on functions means relying on the context created at the moment of definition of a function, in general the *local*, *non-local*, and *global* states defined with respect to a function.

Having more freedom in the use of functions (i.e. having first-class citizen functions) can allow to extend such properties in order to deal with *context* in a more flexible way, providing an alternative to the OO paradigm.

## In Python
- [static methods](https://pythonbasics.org/static-method/)
- [properties](https://pythonguide.readthedocs.io/en/latest/python/property.html)
