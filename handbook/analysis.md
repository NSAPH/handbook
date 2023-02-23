# Introduction to NSAPH GitHub 

[NSAPH Projects GitHub organization](https://github.com/NSAPH-Projects) is a shared account where all NSAPH members 
can collaborate across many projects at once.

The goal is to keep all NSAPH analysis projects at [one location](https://github.com/NSAPH-Projects) to encourage 
internal review, collaboration and reuse. It would also facilitate future data and code curations, migrations, 
and cross-referencing material and documentation.

:::{admonition} New project 
:class: note 
If you are starting a new analysis project, create a repository under [NSAPH Projects](https://github.com/NSAPH-Projects) 
organization on GitHub. You can make contributions to the repository directly, or create a fork under your own account.
:::

:::{admonition} Existing project 
:class: note 
If you already have a working git repository under your own username, transfer its ownership to 
[NSAPH Projects](https://github.com/NSAPH-Projects). You can do that by clicking the following buttons at your 
repository page: "Settings" -> "Danger Zone" -> "Transfer ownership". Have a look at the 
[official GitHub guidelines](https://docs.github.com/en/repositories/creating-and-managing-repositories/transferring-a-repository).
:::

:::{admonition} Existing project from code.harvard.edu
:class: note 
In this case, you can add a new `remote` (or replace the current) in your local git repository. First, navigate to NASPH-Projects on GitHub and create a new repository there. 
Then, navigate to your local git repository and add a new remote like this:

```shell
git remote add nsaph https://github.com/NSAPH-Projects/REPO_NAME.git
# verify new remote 
git remote -v 
```

Last, you should push the repository to the new remote so that all commits stay intact:

```shell
git push -u nsaph master
```
Going forward, make sure to keep the `nsaph` remote up to date!

Alternatively, instead of adding a `nsaph` remote, you can change the address of your current remote with the command `git remote set-url`. 
Have a look at the official documentation [here](https://docs.github.com/en/get-started/getting-started-with-git/managing-remote-repositories#changing-a-remote-repositorys-url).
:::

:::{admonition} Published project 
:class: note 
If you have a git repository of a completed project under your own username that you reference in a publication, 
do not just transfer ownership to [NSAPH Projects](https://github.com/NSAPH-Projects). In this case, you should:

- Transfer ownership and create a **fork** of the repository under your own username; or
- Ask a [NSAPH Projects](https://github.com/NSAPH-Projects) admin to fork your repository. Both repositories should be up-to-date.

This is important so that shared repository URLs are not broken. In this case, do not modify the repository name.
:::


# Tips for using FASSE and NSAPH GitHub 

## Creating a GitHub repository in FASSE

Once you have created a repository on GitHub, you can clone that repository into FASSE, so that you can transfer versions of your files to and from FASSE and GitHub. To clone a GitHub repository into FASSE, start a FASSE Remote Desktop (or Containerized Remote Desktop) session, Open a Terminal window, and write the following lines one-by-one. Note that the first and second lines are different from each other because the first says "http" and second says "https".

```shell
export http_proxy=http://rcproxy.rc.fas.harvard.edu:3128
export https_proxy=http://rcproxy.rc.fas.harvard.edu:3128
cd nsaph_projects/{your project name}
git clone {url of your repository: go to your repository and click on green "Code" button}
```
    
## Uploading files from FASSE to GitHub

As you code in FASSE, it's good practice to upload your code to GitHub often, particular when 

1. you've made or are about to make significant changes  (this way, you'll be able to access the current or old versions later and see the changes you've made), or 
2. you're about to ask someone for coding help or you're about to present your research and people may want to see your code, or even 
3. you yourself want to see your code without logging into FASSE.

To add files from FASSE to GitHub, start a Remote Desktop (or Containerized Remote Desktop) session. 
Open a Terminal window AFTER you're done editing your files (if you open Terminal before you've finished making edits, you'll end up uploading an old version of your code) and type the following lines one by one.

All of the `git status` lines are optional; `git status` simply lets you see what files are in the current folder, 
what files have been changed, what files you're about to commit, etc.

```shell
cd nsaph_projects/{your project name}/{your repository name}
git status
git add {file name or folder/file}
git status
git commit -m "your commit message, in quotes"
git status
git push
YOUR_ACCESS_TOKEN
```

```{note}
If you want to add all the files in your current folder (tip: run `git status` first to make sure you're looking 
at the right files - check that you're adding code only, not data, even if you have separate `code` and `data` folders), 
you can run `git add -A` instead oof `git add {file name or folder/file}`.
```

```{note}
Your commit message should be informative. For example: "update stratification" or "add sensitivity analysis".
```

```{tip}
If you've set up a personal access token for GitHub, you could save your PAT as a text file in your private FASSE folder.
```

## Obtaining GitHub Token

You can follow the following steps, to obtain a GitHub token:

- Log in to your GitHub account and go to your "Settings" page.
- Click on "Developer settings" in the left-hand sidebar.
- Click on "Personal access tokens" and choose "Tokens (classic)".
- Click on "Generate new token" then "Generate new token (classic)" .
- Give your token a description, so you can remember what it is for.
- Select all the scopes available.
- Click on "Generate token".
- Your new token will be displayed. Be sure to copy it and save it for future use, as you won't be able to see it again.
- Once you have generated a token, you can use it to authenticate with the GitHub API or access repositories that require authentication. Keep your token secret and avoid sharing it with others to protect your GitHub account's security.


