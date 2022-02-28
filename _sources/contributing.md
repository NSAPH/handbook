# Contributing on Git

## Fork & Pull Request workflow

Fork & Pull Request workflow is essential when contributing to NSAPH and other open-source projects. Unfortuatelly, it is easy to make mistakes when you are learning the process. Here are the instructions for a standard procedure for creating a fork, making your contribution, issuing a pull request and merging it to the original project.

### Create a Fork

On the GitHub page, click the "Fork" button to create a fork under your account.

![](imgs/fork_pr_fork.png)

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

It is important that you create a new branch for your contribution. It is a proper git workflow and it keeps your changes organized and separated from the master/develop branch, so you can easily switch between them.

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

Now you can update your fork with the lastest  upstream changes.

```
# Fetch from upstream remote
git fetch upstream

# View all branches, including those from upstream
git branch -va

# Checkout your develop branch and merge upstream
git checkout develop
git merge upstream/develop
```

### Submit a Pull Request 

If there are new commits to the upstream `develop` branch, you should rebase your development branch so that merging is straight-forward and conflict-free. You can do that like this: 

```
# Fetch upstream master and merge with your repo's master branch
git fetch upstream
git checkout master
git merge upstream/master

# If there were any new commits, rebase your development branch
git checkout newfeature
git rebase master
```

Then push your contributions to your GitHub fork, and make a pull request on the GitHub web page directly. Make sure to document your contribution with an informative title and description.

![](imgs/fork_pr_docs.png)

You can assign reviewers for your pull request. Follow up with the reviewers and incorporate their suggestions in a new commit to your fork. The new commit will be automatically visible in the pull request.

### Delete the development branch

Once you are done with the development branch, you can delete it:

```
git branch -d newfeature
```

