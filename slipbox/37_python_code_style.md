Python code style practices I don't know
---

Writing code style-compliant code ([python-guide](https://docs.python-guide.org/writing/style/), [PEP 8](https://pep8.org/)) 

check with `pycodestyle`, reformat with `black`, ...

- [ ] using _ before private attribute and methods of a class
- [ ] `return` only at the end; raise exceptions for not normal cases
- [ ] unpacking (assignment to 2+ elements) to swap
- [x] use `__` as ignored variable
- [x] don't compare to `True` and `False`
- [x] use `is None` to check that
- [x] use generator expressions when not reusing lists
- [ ] use generator functions to save memory
- [ ] use list comprehension to change lists values to avoid side-effects - notice this is analogous to applying map functions ;)
- [x] use parenthesis to embed multiple lines: the interpreter will join them