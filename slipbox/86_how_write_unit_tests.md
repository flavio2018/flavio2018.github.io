- [Real Python's Testing in Python](https://realpython.com/python-testing/)
- [`unittest` standard library](https://docs.python.org/3/library/unittest.html)

## Handling side effects
When using an imperative programming language, functions can have side effects such as writing to a file, a DB or changing variables out of the function's scope. When writing tests for a function, it's better to decide in advance whether side effects should be tested as well or not.

Writing unit tests for functions with a look at side effects can be a good way to discover better ways of structuring the code:
> If you find that the unit of code you want to test has lots of side effects, you might be breaking the [Single Responsibility Principle](https://en.wikipedia.org/wiki/Single_responsibility_principle). Breaking the Single Responsibility Principle means the piece of code is doing too many things and would be better off being refactored.

## Using mock data
In object oriented programming, it is frequent that a class' method uses other classes' attributes or methods to achieve its result. When writing unit tests, it is important to localize as much as possible the scope of the test, and thus not to introduce possible external sources of variability in the tested behaviour. So, instead of using real classes, it is better to create mock implementations of the classes that interact with the method being tested, in such a way that they respect the interface that the method expects to interact with.

## Testing stochastic behaviour
Writing machine learning code or code for randomized experiments, it often happens to have a piece of code with *desired randomness* in it. How to test such code? [@sevcikova_automated_2006](@sevcikova_automated_2006.md) is a paper on the topic.