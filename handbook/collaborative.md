# Branch-merge workflow on GitHub

If you'd like to invite your collaborators to review your code, open a "pull request" in your 
[NSAPH Projects GitHub repository](https://github.com/NSAPH-Projects). Follow the steps below:

```{note}
If you contribute to the official [NSAPH Software](https://nsaph-software.github.io/intro.html), 
check out its contribution gudelines. 
```

## Create a new branch

It is important that you create a **new branch** for your contribution. It is a proper git workflow, 
and it keeps your changes organized and separated from the `master`/`main` branch, 
so you can easily switch between them.

```
# Checkout the main (master) branch - you want your new branch to come from main (master)
git checkout main
# Create a new branch and switch to it
git checkout -b newfeature
```

## Commit and push your contribution

You can push your branch to a remote repository:

```bash
git push origin newfeature
```

## Create a pull request

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
their suggestions in a new commit to your branch. The new commit will be automatically visible in the 
pull request after you push them.

Once you are done with the temporary (`newfeature`) branch, you can delete it:
```
git branch -d newfeature
```

```{note}
Check out official documentation from [GitHub](https://docs.github.com/en/get-started/using-git/pushing-commits-to-a-remote-repository) 
and [PyCharm](https://www.jetbrains.com/help/pycharm/commit-and-push-changes.html) on pushing your commits to a remote repository.
```
