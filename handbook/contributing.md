# Collaborative work on GitHub

Opening a "Pull Request" is essential when contributing to NSAPH and other open-source projects. 
It is easy to make mistakes when you are learning the process. 
Here are the instructions for a standard procedure for creating a fork, a branch,
making your contribution, issuing a pull request, asking for review and merging it to the original project.

```{warning}
Do you have write access to the GitHub repository (are you a "collaborator")? If yes, start [here](clone),
otherwise start [here](fork). 
```

```{note}
If you contribute to the official NSAPH software, check its contribution gudelines. 
```

(fork)=
## Create own fork

On the GitHub page, click the "Fork" button to create a fork under your account.

```{figure} imgs/fork_pr_fork.png
---
scale: 90%
align: center 
---
The fork button.
```

Clone **your fork** locally. 

If multiple people are actively contributing to this project, you 
should track the original "upstream" repo that you forked. To do that, you need to 
add a remote:

```
# Add 'upstream' repo to list of remotes
git remote add upstream https://github.com/UPSTREAM-USER/ORIGINAL-PROJECT.git
# Verify the new remote named 'upstream'
git remote -v
```

Next, you should create a new working branch as described [here](branch).

(clone)=
## Clone the repository

Clone the repository to your local machine as follows:
```
git clone https://github.com/NSAPH-Projects/PROJECT.git
```

(branch)=
## Create own branch

It is important that you create a **new branch** for your contribution. It is a proper git workflow, 
and it keeps your changes organized and separated from the master/main branch, so you can easily switch between them.

```
# Checkout the main branch - you want your new branch to come from main
git checkout main
# Create a new branch and switch to it
git checkout -b newfeature
```

(sync-fork)=
## Sync and rebase your fork

If you have write access to the GitHub repository and you didn't need to create own fork, 
proceed to [here](open-pr).

Otherwise, if there are new commits to the upstream `main` branch, you should rebase your 
working branch so that merging is straight-forward and conflict-free. 
You can do that like this: 

```bash
# Fetch from upstream remote
git fetch upstream
git checkout newfeature
git rebase upstream/main
```

```{note}
Read more about syncing the fork using GitHub UI 
[here](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/syncing-a-fork).
```

(open-pr)=
## Create a pull request

Finally, you can push your branch to a remote repository:

```bash
git push origin newfeature
```

In the GitHub UI, you will see a button giving you the option to create a pull request.

Make sure to document your contribution with an informative title and description.

```{figure} imgs/fork_pr_docs.png
---
scale: 80%
align: center 
---
Describe your contribution.
```

You can assign reviewers for your pull request after creating one. Follow up with the reviewers and incorporate 
their suggestions in a new commit to your fork. The new commit will be automatically visible in the pull request after you push them.

Once you are done with the temporary (`newfeature`) branch, you can delete it:
```
git branch -d newfeature
```

```{note}
Check out official documentation from [GitHub](https://docs.github.com/en/get-started/using-git/pushing-commits-to-a-remote-repository) 
and [PyCharm](https://www.jetbrains.com/help/pycharm/commit-and-push-changes.html) on pushing your commits to a remote repository.
```
