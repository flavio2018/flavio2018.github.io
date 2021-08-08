---
title: Pro Git
authors: Scott Chacon
year: 2014
abstract: 
---
# Pro Git
[Resource on the Web](https://git-scm.com/book/en/v2)

## 1. Getting started
- Git does not think about the project history as a sequence of *changes* made to its files (delta-based version control), but rather as a sequence of snapshots to the entire project tree, that is efficiently done storing references to of files that didn't change rather than copies of the.
- A file that's part of a git repository can be in one of three states: 
	- modified: it has changes that are not present in the last snapshot saved to the database; 
	- staged: its current state is the one selected to go in the next commit (snapshot) to the database;
	- committed: changes made in the staged version were saved to the database.
- The three areas of a git project that correspond to the states above are:
	- working tree: a decompressed copy of a snapshot in the database which you can work and make changes on;
	- staging area (or index): a file that contains the references to all changes that will be included in the next commit;
	- git directory (repository): the local database that contains all the history of changes made to the project.

## Git Basics
- `git log` has a lot of cool options
- there are some ways of undoing things in git, depending on what you want to undo. 
	- `git commit --amend` allows you to modify both the contents and the message of the last commit. 
	- `git checkout -- <filename>` is a potentially dangerous command that discards **permanently** all uncommitted changes made in `<filename>`.
	- `git restore --staged` and `git restore <filename>` are two alternatives to the previous commands introduced in a relatively recent version of git.
- remote repositories are copies of the same project you're working on that are *not your local repository*. It is possible that these copies are on a server, on a collaborator's machine or even on your own machine - they're simply not your local repository.
- remote repositories can be added (the one a project is cloned from is automatically added as `origin`), and changes can be `fetch`ed and - with permissions - even pushed there.
- `git fetch` is part of what happens with `git pull`. Indeed, `git fetch` only copies changes made in a remote repository in the local one. By default, it does not try to `merge` the changes into your local branches. On the other hand `git pull` automatically does so provided that you're tracking the remote branch you're pulling from with your local branch.
- the general form of the command used to share changes is `git push <remote> <branch>`. Now it's clearer what that means. 

## Git Branching
>Unlike many other VCSs, Git encourages workflows that branch and merge often, even multiple times in a day. Understanding and mastering this feature gives you a powerful and unique tool and can entirely change the way that you develop.
- to properly understand branches it is useful to remind that a git repository contains *objects* that are either *blobs* (representations of files), *trees* (representations of directories) and *commits*.
- a branch in Git is just a pointer to a commit; the master branch usually moves on with the commits we make "on that branch". The information about which branch we are currently in is stored by Git in the `HEAD` variable.
- creating a new branch, moving in it (`checkout`) and making a new `commit` would simply cause the new commit to refer to the previous one (in the old branch!) as its parent, having the two branches pointers pointing at the old and new commits, respectively.
![[git_branch.png]] 
- ==note==: "checking out" to a branch therefore simply means moving the `HEAD` to point to the pointer of the branch
- ==note==: when you're on a branch `git log` will only show commits made on that branch by default
- ==note==: `git switch` can now be used in place of `git checkout` to move (or create and move) to a new branch
- ==note==: the terming "fast forward" in git merges simply means that no divergent changes on some portion of code were made in the new branch with respect to the old branch we are merging on; therefore, Git simply "moves the pointer forward" to the last commit on the new branch
- another simple case of merging is the one in which the change history did diverge (the branch master contains changes that are not in the other branch, and vice versa), but none of these changes are conflicting (i.e. on the same portion of code). In this case, Git simply starts from the lowest common ancestor version of the two files and modifies the parts that are changed in each branch. All this is possible thanks to snapshots of file changes (*blobs*).
- of course, branches enable implementing workflows. A common workflow in git is to have long running branches. In a project of medium-to-big complexity there will usually be a completely stable and tested branch, usually `main` or `master`, which is usually the production one. Then a `test` or `development` branch where all new work is done before including it in the stable branch. This branch can further divide into topic branches, to develop individual features independently.
- creating topic branches is feasible, easy and useful in projects of any size.