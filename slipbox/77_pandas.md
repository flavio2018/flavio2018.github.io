# Pandas
This is a note I will use to learn better Pandas. I'm going to start from [Tom Augspurger's guide](https://tomaugspurger.github.io/modern-1-intro) on modern Pandas.

## 1. `df.pipe()`
[In the docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.pipe.html?highlight=pipe#pandas.DataFrame.pipe)

The first useful tool is the `pipe` function that can be applied to a DataFrame. It allows to chain functions that take DataFrames as inputs and return one as output, while keeping the code clean and readable

They are inspired by R's `%>%` (read "pipe") operator, that chains transformations over data sources seamlessly. The syntax of the operator is: `a %>% b %>% c`, which means that function `c` is applied to the output of function `b` that is called with argument `a` (i.e., each function in the pipe takes the expression to the left of `%>%` as argument). You can even add some more arguments to the calls of the functions in the pipe, and in Pandas you can control even more precisely the function calls and the arguments passed.

## 2. `df.query()`
[In the docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.query.html?highlight=query#pandas.DataFrame.query)

This method allows to select the rows of the DataFrame where some boolean condition on the columns is satisfied. It feels like this is something I've wanted to do for a long time. For example, assuming to have a DF of numerical values with columns `a, b, c`, `df.query("a > b")` will return the rows where the value in column `a` is strictly greater that that in column `b`.

[Notes about efficiency in Jake VanderPlas Book](https://jakevdp.github.io/PythonDataScienceHandbook/03.12-performance-eval-and-query.html)

## 3. `df.rename()`
Probably the clearest method to rename columns (or rows) of a DataFrame. It takes either 
- a `dict` as input, with the old rows/columns names as index and the new ones as values, or
- a function, that maps each old name to a new one.