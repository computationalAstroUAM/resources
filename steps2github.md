# Using git and GitHub

If you need to: create an account in github and learn the basics with the [basic github resources](https://try.github.io/) and [a cheat sheet](https://zeroturnaround.com/rebellabs/git-commands-and-best-practices-cheat-sheet/). [Here](https://scientific-programming.github.io/version-control/) you have an overview of what is version control and a an other tutorial, plus some useful ideas on collaborative coding.

Github provides free account upgrades to students and anyone working at a educational/research institute, which allow you to have your own private repositories. To get this upgrade, once you have a personal account, go to this page and fill in the form: https://education.github.com/discount_requests/new

The recommended steps to contribute to a repository are:

1. Fork and clone: Get a copy from the GitHub repository 
1. Update your personal copy
1. Track upstream: keeping your copy up-to-date with the main one
1. Steps to follow when working on a new (big) feature: Branch, Contribute, Commit, (Merge) and Push.
1. Submit a Pull Request to the main a repository code.

## Fork and clone: Get a copy from a GitHub repository 

Once you have your GitHub account and are familiar with the basic git vocabulary, create your own a repository copy:

1. Go to https://github.com/computationalAstroUAM/[repo name]

2. Click 'Fork' there (right upper corner).
 
The next step is to get your copy of the repository onto your computer:

1. In your computer, go to your home directory (or wherever you want to have the repository).

2. Clone there the repository, from your OWN local repository:

`git clone https://[git username]@github.com/[git username]/[repo name]`

You'll be prompt for your GitHub username and password.

## Updating your a repository copy.

Ensure that the remote is the correct one: 

`git remote -v`

If you need to reset the remote link:

`git remote set-url origin https://[git username]@github.com/[git username]/[git repository]`
   
Update your personal copy:

`git push origin master`

## Track upstream: keeping your copy up-to-date with the main one

This instructions follow the recommendations on [syncing a fork from GitHub](ttps://help.github.com/articles/syncing-a-fork/). To make sure that your version remains up to date with
the main version, set the upstream tracking on the command line (chenge master to main if your branch is called main instead):

`git remote add --track master upstream https://[git username]@github.com/computationalAstroUAM/[repo name]`

Now, every time you need to apply the changes that have been made to the main version to yours, navigate to your a repository directory and run on the command line:

```
git fetch upstream
git merge upstream/master
```

## Working on a new (big) feature

### Branch, contribute and Commit

To start working on new feature, create a separate feature branch:

`git checkout -b feature`

You can check the branches you have by:

`git branch`

And switch between them with:

```
git checkout master
git checkout feature
```

Once some changes have been made in the branch, stage them
and commit:

```
git add .
git commit -am "Add a comment here"
```

### About conflicts
If there are [conflicts](https://docs.github.com/en/free-pro-team@latest/github/collaborating-with-issues-and-pull-requests/resolving-a-merge-conflict-using-the-command-line), git will let you know in which files. Open those files and the conflics will be indicated with `<<<<<<<`. The changes from the HEAD or base branch will appear after the line `<<<<<<< HEAD`. Next, `=======` divides your changes from the changes in the other branch, followed by `>>>>>>> BRANCH-NAME`. You need to decide what you keep. Once you are done, commit:

```
git commit -am "Resolved merge conflict."
```

and continue pushing, requesting a pull request, etc.


### (Merge and) Push

You can push changes with:

`git push origin feature`

Alternatively, you can merge the changes with the main
branch first, and then push:

```
    git checkout main
    git merge feature
    git push origin main
```

## Submit a Pull Request

When you are ready to update the main a repository code, go to your GitHub repository page, click "New pull request" to create a Pull Request from your
latest commit. It will be applied by someone with
administrator main version  rights after review.
