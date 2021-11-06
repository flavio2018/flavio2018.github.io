---
title: Home - Cookiecutter Data Science
aliases: ["Home - Cookiecutter Data Science"]
authors: DrivenData
year: 2021
abstract: A project template and directory structure for Python data science projects.
---
# Home - Cookiecutter Data Science

<p style="text-align: right">
<a href="
https://drivendata.github.io/cookiecutter-data-science/
">
<i>
DrivenData, 2021</i>
</a>
</p>

***

Advantages of standardized Data Science project structure: 
- it does not require a newcomer much overhead to understand (parts of) the project, even if it does not know the structure, because it's self-documenting
- it can make everyone more confident about the results of analyses
- makes it easier to come back to old(ish) analysis after some time

The authors of the document have some conventions developed over time. They can be seen as the first principles over which the proposed structure is built and they regard several different areas of project management and development.

Data · They never modify the original data source. They write code so that analysis can be reproduced only starting from the raw data and the source code provided. To re-run an analysis to obtain a specific result it should not be necessary to re-run the whole pipeline. Large files should be synced in other ways than with version control.

Notebooks · are not easy to collaborate over and are not made to run analyses (they are not easily reproducible). They are good for explorations and visualization of final results - two goals that should be well distinguished also in the project structure. Code that is repeated across notebooks should be refactored in the appropriate `src` subfolder, depending on its purpose.

Analysis as DAG · The way analyses usually work is that starting from a data source you do some preprocessing or manipulations and then run some kind of analyses on the data. The authors advocate for automatizing the steps of manipulation of the data using tools such as `make` or similar others. 

Environment · In order to reproduce analyses, the environment should be the same as the one that produced them the first time. So, environments should be handled with `virtualenv` or Docker for more complex needs.

Secrets · Keep secrets out of GitHub placing them all in a `.env` file that is added to the `.gitignore` and nicely loaded in scripts and notebooks using a package called `python-dotenv`.

