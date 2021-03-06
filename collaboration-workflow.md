# Workflow for Collaboration using Git and GitHub

Suppose you've got some software you're working with and have found a bug. Or maybe you're passionate about contributing a new feature to a favorite project. Or you want to share your work with your research group. In all of these cases, Git and GitHub serve as excellent tools for building and maintaining collaborative relationships. If you're not familiar with Git, you can start by thinking of it as bookkeeping software for tracking changes made to repositories of software. GitHub is a publicly available collaboration service built around Git. While Git tracks changes to code, GitHub also tracks issues and bugs, documentation, discussions, and has an interface for automating tedious processes like code formatting and error checking.

Because the purpose of Git and GitHub is collaboration, every project needs a shared plan for how to make collaboration work. We suggest a commonly used workflow consisting of three parts: an initial setup step, and then two loops. Setup involves forking an upstream repository and cloning the fork to your local development environment. The longer, outer loop involves merging upstream changes to your fork, making your own changes, then pushing them back upstream. The shorter, inner loop involves committing incremental changes to a branch on your own local clone. We will call these the "pull request loop" and the "commit loop".

The instructions below assume you have a GitHub account, and that you have Git software installed and configured on your local machine that is usable from a terminal.

## Setup

Setup is a one-time process for each repository you wish to work on, and involves two steps.

1. Fork the upstream repository to your GitHub account.

    1. Login at https://github.com or a link to the upstream repository. We will be working on https://github.com/uabrc/uabrc.github.io.
    2. On the repository page, click the fork button near the top-right of the page, then follow the instructions to create a fork on your account.
    3. Make note of the URL created for your fork.
    
2. Clone your remote fork to your local machine.

    1. Open a terminal on your local machine.
    2. Change directories to where you want the cloned repository to be located.
    3. Use the clone command with the URL of your fork as `git clone $URL`.

## The Pull Request Loop

The pull request loop consists of several steps, and comes into play whenever you have a new feature or fix you'd like to make.

1. Fetch changes from the upstream repository to your fork.

    1. Login at https://github.com or a link to your fork.
    2. On the repository page, find and click the drop-down labeled "Fetch Upstream", click it, then click "Fetch and Merge".
    3. Now, left of that button, you should see "This branch is up to date with $UPSTREAM-REPO"

2. Pull changes from your remote fork to your local repository.

    1. Open a terminal on your local machine.
    2. Change directories to your local repository.
    3. Checkout the `main` branch using the checkout command as `git checkout main`.
    4. Use the pull command as `git pull origin main`.

3. Create a new branch on your local repository.

    1. Think of an appropriate name for your branch. For features consider using `feat-...` and for fixes `fix-...`. Short, memorable, desscriptive names are best.
    2. Use the branch command as `git branch $BRANCH-NAME`.
    3. Checkout the branch as `git checkout $BRANCH-NAME`.

4. Enter the [commit loop](##The-Commit-Loop) and make changes. This is the part where you get to think of what it is you want to do that is related to the feature or fix you want to implement.

5. Push changes to your remote fork.

    1. Use the push command as `git push origin $BRANCH-NAME`.
    2. Note we don't want to merge back into main just yet! That will automatically happen after we make our pull request and fetch upstream changes.

6. Create a pull request from your fork to the upstream repository.

    1. Login to your fork.
    2. On the repository page, find and click "Pull Requests".
    3. Find and click the "New Pull Request" button.
    4. The first drop-down is the `base repository` and should be set to the upstream repository
    5. The second is the `base branch` and should be set to the upstream branch `main`.
    6. The third drop-down is the `head repository` and should be set to your fork
    7. The fourth drop-down is the `compare branch` and should be set to your fork branch `$BRANCH-NAME`.
    8. Once these are set correctly, there should be a button "Create pull request". Please click that.
    9. You'll be taken to an "Open a pull request" page. Please give the pull request a brief, meaningful title and helpful comments describing your changes so that your collaborators can understand your intent.
    10. Click the "Create pull request" button.

Now your collaborators will review your pull request and either reject it, accept it, or propose additional changes. For any new fixes and features, start over from step (1) to be sure you incorporate the changes made by other collaborators.

## The Commit Loop

The commit loop applies as you make incremental changes toward a specific fix or a new feature, and should all occur on the same branch. This loop is much tighter and involves more frequent usage than [the pull request loop](##The-Pull-Request-Loop). The first step is to make sure you are on the appropriate working branch using the `git checkout $BRANCH-NAME` command.


1. Make a set of minimal, yet complete, changes. Experience and discipline help here for determining what is both minimal and complete, and will be built up from practice and feedback. When we say complete, we mean that the code still functions as expected. When we say minimal, we mean there are no other changes beyond what is needed.
2. Commit those changes with a brief and descriptive $MESSAGE using `git commit -m $MESSAGE`. Commit messages should be forward-looking. Think about how a future version of you will read those messages, and what you want future you to take away from that message, because some day you may need to review your changes!

Be sure not to commit any secret information! NEVER commit passwords, personal authorization tokens, usernames, email, or any other protected, regulated or secret information.

Be sure not to commit machine-specific information. Avoid committing file paths that only apply on your local machine, as other people won't be able to use them.

Be sure not to commit large data files and other artifacts. These files are treated as binary blobs, and are completely replaced each time a new version is committed. A 50 MB file committed twenty different times will bring your repository over 1 gigabyte in size!
