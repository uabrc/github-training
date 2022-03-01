# Advanced Operations

There are other operations and techniques we haven't covered yet that may prove useful once the basics of this workflow are set. These include starting your own repository, checking changes using diffs, merging branches locally, resolving merge conflicts, stashing changes, rolling back changes locally, and visualizing the branch graph. Before wading into the more advanced operations, we highly recommend using a graphical git tool. VSCode is easy to use and has most features of git built in with excellent graphical aids.

## Starting Your Own Repository

Starting your own repository is relatively simple, and there are three common steps of greatest importance. (1) You can create the repository on a local machine by navigating to the main folder you intend to store the repository and using `git init`. (2) Consider creating a `.gitignore` file to ignore files that shouldn't be under version control. Files that _should_ be under version control include code files, documentation, small test cases, and general configuration files including the `.gitignore` file. Files that should _not_ be under git version control include large data files, secret information, operating system files, temporary code files, and final artifacts like executables. (3) You can add a remote repository origin using `git remote add origin $URL`.

## Using Diffs

A diff is a visualization of the changes made to a file. Diffs are interpreted line-by-line or character-by-character, and show what parts have been removed and what parts have been added, when comparing two versions of a file. Diffs are extremely helpful for seeing how a file has changed over time.

You can use diffs to identify what changes have been made to given files. Git has a built in diff function as `git diff $FLAGS`, which has [many use cases](https://git-scm.com/docs/git-diff) we won't go over here. Instead, we highly recommend using a graphical diff tool, of which many are available. VSCode has a high-quality diff tool built in.

## Merging Branches Locally

Sometimes you'll make changes to a fix branch that prove useful on a feature branch you're also working on, but you can't wait for the fix to go through review before you make use of it. You can merge the fix branch into the feature branch by first `git checkout $feat-branch` followed by `git merge $fix-branch`. It's assumed that none of the fix changes conflict with the feature changes. If there are conflicts, the merge will be stopped, leaving your git in an incomplete merge state where the conflicts must be resolved. Here is where the "minimal, yet complete" changes are important. Each change should be as small as possible to minimize the risks of conflicts. It is much easier to avoid conflicts than to resolve them when they arise, but sometimes they are unavoidable.

## Resolving Merge Conflicts

We highly recommend using a graphical tool for resolving merge conflicts. VSCode allows viewing all of the context of a file when reviewing conflicts, which can make the process smoother. Conflicts are visualized by git directly in a temporary version of the affected file. Any conflicting changes are set apart from each other in the following format. The upper part, above the `=======` is from the "current" branch and is called the "current changes". The lower part is from branch being merged in and is called the "incoming changes".

```text
<<<<<<< HEAD
content on the current branch
=======
some other content from the branch being merged into the current branch
>>>>>>> new_branch_to_merge_later
```

## Stashing Changes

TBD

## Rolling Back Changes

TBD

## Git Graph

TBD
