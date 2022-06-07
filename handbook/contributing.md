# Contributing on Git

## Fork & Pull Request workflow

Fork & Pull Request workflow is essential when contributing to NSAPH and other open-source projects. Unfortuatelly, it is easy to make mistakes when you are learning the process. Here are the instructions for a standard procedure for creating a fork, making your contribution, issuing a pull request and merging it to the original project.

*Overview*:
* [Create a Fork](#create-a-fork)
* [Add your contribution](#add-your-contribution)
* [Keep your fork up to date](#keep-your-fork-up-to-date)
* [Submit a Pull Request from your fork](#submit-a-pull-request-from-your-fork)
* [Delete the development branch](#delete-the-development-branch)

### Create a Fork

On the GitHub page, click the "Fork" button to create a fork under your account.

```{figure} imgs/fork_pr_fork.png
---
scale: 90%
align: center 
---
The fork button.
```

Clone the fork to your local machine as follows:

```
git clone git@github.com:USERNAME/FORKED-PROJECT.git
```

````{tip}
If you contribute to the official NSAPH software, check its contribution gudelines. 

You may need to build on the `develop` branch instead of the `master/main` branch. To fetch the develop branch, type:
```
git checkout --track origin/develop
```
````

### Add your contribution

It is important that you create a new branch for your contribution. It is a proper git workflow, and it keeps your changes organized and separated from the master/develop branch, so you can easily switch between them.

```
# Checkout the develop branch - you want your new branch to come from develop
git checkout develop

# Create a new branch 
git branch newfeature

# Switch to your new branch
git checkout newfeature
```
### Keep your fork up to date

If multiple people are actively contributing to this project, or you plan to work on it for a longer period (ie, your contribution is not just "a quick fix"), you should track the original "upstream" repo that you forked. To do that, you need to add a remote:

```
# Add 'upstream' repo to list of remotes
git remote add upstream https://github.com/UPSTREAM-USER/ORIGINAL-PROJECT.git

# Verify the new remote named 'upstream'
git remote -v
```

Now you can update your fork with the latest upstream changes.

```
# Fetch from upstream remote
git fetch upstream

# View all branches, including those from upstream
git branch -va

# Checkout your develop branch and merge upstream
git checkout develop
git merge upstream/develop
```

### Submit a Pull Request from your fork
*Overview:* There are three steps in creating a PR from your fork.
1. Sync the fork, rebase if necessary.
2. Push your changes to your fork.
3. Make pull requests from your fork.

#### Sync the fork
**Commandline**:
```
# Fetch upstream master and merge with your repo's master branch
git fetch upstream
git checkout master
git merge upstream/master
```
If there are new commits to the upstream `develop` branch, you should rebase your development branch so that merging is straight-forward and conflict-free. You can do that like this: 

```
# If there were any new commits, rebase your development branch
git checkout newfeature
git rebase master
```
**GitHub web**:

```{figure} imgs/fetch-upstream-drop-down.png
---
scale: 60%
align: center 
---
Dropdown options to fetch
```

If the upstream commits look good, click "Fetch and merge"
```{figure} imgs/fetch-and-merge-button.png
---
scale: 40%
align: center 
---
Fetch and merge button
```
Read more about syncing the fork using GitHub UI [here](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/syncing-a-fork).

#### Push your contributions to your GitHub fork 
[Command line](https://docs.github.com/en/get-started/using-git/pushing-commits-to-a-remote-repository)

[PyCharm](https://www.jetbrains.com/help/pycharm/commit-and-push-changes.html)


#### Make a pull request on the GitHub web page directly 
Follow the steps [here](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request-from-a-fork) to make a pull request from your fork. Make sure to document your contribution with an informative title and description.

```{figure} imgs/fork_pr_docs.png
---
scale: 80%
align: center 
---
Describe your contribution.
```

You can assign reviewers for your pull request after creating one. Follow up with the reviewers and incorporate their suggestions in a new commit to your fork. The new commit will be automatically visible in the pull request.

### Delete the development branch

Once you are done with the development branch, you can delete it:
```
git branch -d newfeature
```
