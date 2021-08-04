# Python memory usage
Memory management in Python heavily relies on references, since in Python variable names are references to objects in memory. Since Python 3, the language has a garbage collector that is based on reference counting, i.e. memory is freed whenever an object has no more references pointing towards it.

## References in function calls
From [this blog post](https://pythonspeed.com/articles/function-calls-prevent-garbage-collection/).

When using nested function calls, it might happen that although an object is never going to be used again within a function scope, a reference to it is still kept, and therefore the memory that the object occupies cannot be freed as soon as one might want. 

To prevent this, it is useful to avoid keeping references to objects in scopes where those objects are never going to be used again. There are several ways to do so, that are suggested in the original post.

## Kinds of memory
From [this blog post](https://pythonspeed.com/articles/measuring-memory-python/).

Using `psutils` to track memory usage of a Python script corresponds to tracking a specific kind of memory usage, i.e. *resident memory*. This is the amount of RAM space used by the process in a specific moment of time. However, a process may also have portions of *swapped* memory, i.e. data that were moved to the hard drive by the OS to free some RAM space for other processes.