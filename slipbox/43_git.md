# Git
[@chacon_pro_2014](@chacon_pro_2014.md)

---

Git (or any other Version Control Software) is a necessary tool to manage different versions of a codebase and, by extension, to organize a coding workflow.

Several different workflows [already exist](https://dev.to/hardkoded/how-to-organize-your-git-branches-4dci), but they are generally intended for more traditional development needs than "data science" ones; developing a workflow for such development scenarios is still [an open question](https://resources.github.com/downloads/development-workflows-data-scientists.pdf).

[44_workflow](44_workflow.md)

I will need to know better the git tool in order to leverage its potential in helping implementing a development workflow. 

## Branching
The first and most basic functionality I will need to know better is **branching**. As far as I understand, branching is a tool which allows git to keep track to local changes made to the codebase without the need to create multiple actual copies of the project files and folders. Git does so by keeping track of the differences between the initial version of the project and the current state of the project version one is working on. 
Branching is, as far as I get, a ***local*** operation; indeed, we can list *remote* branches of a repository, i.e. branches present on other local repositories of other contributors to the project.

## Committing
Committing is the basic action you do to record the changes you do to the codebase. A "commit" should be seen as a snapshot of the current state of the file, after some changes have been made.

The key point is *when* to commit: too rare commits tend to include lots of changes and this is bad for two reasons:
1. they're not useful if you want to *partially* roll back changes you did in that commit;
2. they're hard to understand from the outside or after some time; in particular, it's hard to write a good commit message for that commit ([here a post on why it's important](https://chris.beams.io/posts/git-commit/)).

[97_good_commits_messages](97_good_commits_messages.md)

## Forking
[Forking on GitHub Guides](https://guides.github.com/activities/forking/)

The forking process is at the basis of contributing to a project in GitHub. Usually, contributions happen in local copies of a project's repository, called *forks*. The contributor creates a branch in its own fork of the repository which has a meaningful name, usually referring to some new feature he/she is working on. Then, once the code is ready to be reviewed by the repository maintainers, the contributor can issue a *pull request*, which starts a discussion process with the maintainers about the changes made. During this process new commits and changes can be added by the contributors to his/her own version of the project, and finally they can be accepted or rejected by the maintainers.

## Git data model
from https://missing.csail.mit.edu/2020/version-control/

- "In Git terminology, a file is called a “**blob**”, and it’s just a bunch of bytes. A directory is called a “**tree**”, and it maps names to blobs or trees. A **snapshot** ("commit") is the top-level tree that is being tracked."
- "In Git, a history is a directed acyclic graph (DAG) of snapshots. [A snapshot has] a set of parents rather than a single parent because a snapshot might descend from multiple parents, for example, due to combining (merging) two parallel branches of development."
- a commit has parents, metadata, *and the top-level tree*
```
type commit = struct {
    parent: array<commit>
    author: string
    message: string
    snapshot: tree
}
```
- "Blobs, trees, and commits are unified in this way: they are all objects. In Git data store, all objects are content-addressed by their SHA-1 hash."
- "**References** are pointers to commits. Unlike objects, which are immutable, references are mutable (can be updated to point to a new commit). In Git, “where we currently are” is a special reference called “HEAD”."