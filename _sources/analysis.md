# Introduction to NSAPH GitHub 

[NSAPH Projects GitHub organization](https://github.com/NSAPH-Projects) is a shared account where all NSAPH members 
can collaborate across many projects at once.

The goal is to keep all NSAPH analysis projects at [one location](https://github.com/NSAPH-Projects) to encourage 
internal review, collaboration and reuse. It would also facilitate future data and code curations, migrations, 
and cross-referencing material and documentation.

:::{admonition} New project 
:class: note 
If you are starting a new analysis project, create a repository under [NSAPH Projects](https://github.com/NSAPH-Projects) 
organization on GitHub. You can make contributions to the repository directly, or create a fork under own account.
:::

:::{admonition} Existing project 
:class: note 
If you already have a working git repository under own username, transfer its ownership to 
[NSAPH Projects](https://github.com/NSAPH-Projects). You can do that by clicking the following buttons at your 
repository page: "Settings" -> "Danger Zone" -> "Transfer ownership". Have a look at the 
[official GitHub guidelines](https://docs.github.com/en/repositories/creating-and-managing-repositories/transferring-a-repository).
:::

:::{admonition} Published project 
:class: note 
If you have a git repository of a completed project under own username that you reference in a publication, 
do not just transfer ownership to [NSAPH Projects](https://github.com/NSAPH-Projects). In this case, you should:

- Transfer ownership and create a **fork** of the repository under own username; or
- Ask a [NSAPH Projects](https://github.com/NSAPH-Projects) admin to fork your repository. Both repositories should be up-to-date.

This is important so that shared repository URLs are not broken. In this case, do not modify the repository name.
:::


# Tips for Using FASSE and NSAPH GitHub 

## Creating a GitHub repository in FASSE

Once you have created a repository on GitHub, you can clone that repository into FASSE, so that you can transfer versions of your files to and from FASSE and GitHub. To clone a GitHub repository into FASSE, start a FASSE Remote Desktop (or Containerized Remote Desktop) session, Open a Terminal window, and write the following lines one-by-one. Note that the first and second lines are different from each other because the first says "http" and second says "https".

    export http_proxy=http://rcproxy.rc.fas.harvard.edu:3128
    export https_proxy=http://rcproxy.rc.fas.harvard.edu:3128
    cd nsaph_projects/{your project name}
    git clone {url of your repository, which should end in .git and you can copy from github: go to your repository and click on green "Code" button}

## Uploading files from FASSE to GitHub

As you code in FASSE, it's good practice to upload your code to GitHub often, particular when 1) you've made or are about to make significant changes  (this way, you'll be able to access the current or old versions later and see the changes you've made), or 2) you're about to ask someone for coding help or you're about to present your research and people may want to see your code, or even 3) you yourself want to see your code without logging into FASSE.

To add files from FASSE to GitHub, start a Remote Desktop (or Containerized Remote Desktop) session. Open a Terminal window AFTER you're done editing your files (if you open Terminal before you've finished making edits, you'll end up uploading an old version of your code) and type the following lines one by one.

Note 1: All of the `git status` lines are optional; `git status` simply lets you see what files are in the current folder, what files have been changed, what files you're about to commit, etc.

Note 2: If you want to add all the files in your current folder (tip: run `git status` first to make sure you're looking at the right files - check that you're adding code only, not data, even if you have separate "code" and "data" folders), you can run `git add -A` instead oof `git add {file name or folder/file}`.

    cd nsaph_projects/{your project name}/{your repository name}
    git status
    git add {file name or folder/file}
    git status
    git commit -m {your commit message, in quotes, for example: "update stratification" or "add sensitivity analysis"}
    git status
    git push
    {your personal access token, if you've set one up (you could save your PAT as a text file in your private FASSE folder)}


# More FASSE Tips

## Using RStudio on FASSE

There are two ways to use RStudio and access your files on FASSE: 1) RStudio Server or 2) Remote Desktop (or Containerized Remote Desktop). You may find RStudio Server to be the easiest to use because you can use shortcuts like Cmd + C (or Ctrl + C) there. Meanwhile, Remote Desktop (or Containerized Remote Desktop) is useful because you can use Terminal there to upload files to GitHub.

When starting a RStudio session, you may want to use the following options. Partition: "fasse" (or "test" if "fasse" is taking too long to start because other user(s) are using that partition too). R version to be loaded with Rstudio: "R/4.0.5-fasrc02 Comp gcc" (or whatever version of R you're looking to use). Location of your R_LIBS_USER folder: "$HOME/apps/{your project name}/R_4.0.5:$R_LIBS_USER". More on this last option below.

## Installing R Packages

If you don't want to install the same R packages over and over again each time you open FASSE, create a $R_LIBS_USER file. [This link](https://docs.rc.fas.harvard.edu/kb/r-packages/) explains some of this, and below are some tips for setting up your $R_LIBS_USER, but you might want to go to Harvard FAS Research Computing's weekly [office hours](https://www.rc.fas.harvard.edu/training/office-hours/) to get more help.

You'll want to edit your .bashrc file (which you can see in your home folder by clicking "View" > "Show Hidden Files") to be the following. In this example, the user wants to use R version 4.0.5. `projects`, `ml_r4`, and `ml_rstudio` are examples of Terminal commands that you may to create "aliases" (i.e., shortcuts) for. After you do this, you can open a Terminal window (or more than one Terminal window) and type your aliases to, in this example, change the working directory to the `/n/dominici_nsaph_l3/projects/projects` folder or load RStudio (which requires loading R first).

    # .bashrc

    # Source global definitions
    if [ -f /etc/bashrc ]; then
    . /etc/bashrc
    fi

    export R_LIBS_USER=$HOME/apps/{your project name}/R_4.0.5:$R_LIBS_USER

    # Aliases
    alias projects='cd /n/dominici_nsaph_l3/projects'
    alias ml_r4='module load gcc/9.3.0-fasrc01 R/4.0.5-fasrc02'
    alias ml_rstudio='module load rstudio/1.1.453-fasrc01'

If you want to use your $R_LIBS_USER to access R packages you've installed in previous sessions (as already described above, this allows you to not have to `install.packages()` in RStudio every time you start a FASSE session), you'll need to create a folder, which is called `apps/R_4.0.5` in this example (that is, this example requires a folder called "R_4.0.5" within a folder called "apps"), in your private private home folder.
