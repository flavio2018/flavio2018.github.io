It is particularly my concern to apply these principles to Jupyter Notebooks, Data Science, Deep Learning scenarios, implemented in Python.

According to [this website](https://cloud.google.com/blog/products/ai-machine-learning/best-practices-that-can-improve-the-life-of-any-developer-using-jupyter-notebooks) about best practices in Jupyter Notebook creation, the following general software development best practices should still be applied:
-	**version control** & code review: is there a specific way to use such systems?
-	**separate environments** for production and development: how to do this?
-	use comprehensive **test suites**
-	continuous integration, i.e. automatically run testing at each commit
-	continuous deployment, i.e. automatically add the versions which pass CI tests to the production environment

Furthermore, for Jupyter Notebooks in particular, it is advisable to create them in such a way that they can be run entirely by anyone and provide all the necessary context to do so[^reproducible].

Also, Jupyter Notebooks can be parameterized using the [Papermill](https://github.com/nteract/papermill) tool, hence enabling to execute the whole Notebook with different parameters configurations e.g. for hyper-parameters grid search.

Check out [this YouTube video](https://www.youtube.com/watch?v=EKUy0TSLg04) of a SciPy conference in which some best practices are presented and discussed.

[^reproducible]: [82_reproducible_data_science](82_reproducible_data_science.md)