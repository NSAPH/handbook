## Using RStudio on FASSE

There are two ways to use RStudio and access your files on FASSE:

1. RStudio Server or 
2. Remote Desktop (or Containerized Remote Desktop). You may find RStudio Server to be the easiest to use because you can use shortcuts like Cmd + C (or Ctrl + C) there. Meanwhile, Remote Desktop (or Containerized Remote Desktop) is useful because you can use Terminal there to upload files to GitHub.

When starting a RStudio session, you may want to use the following options:

- Partition: "fasse" (or "test" if "fasse" is taking too long to start because other user(s) are using that partition too). 
- R version to be loaded with Rstudio: `R/4.0.5-fasrc02 Comp gcc` (or whatever version of R you're looking to use). 
- Location of your R_LIBS_USER folder: `$HOME/apps/{your project name}/R_4.0.5:$R_LIBS_USER`. More on this last option below.

## Installing R Packages

To install R packages in RStudio Server in the FASEE cluster, you will need to configure the proxies according to our [Proxy Settings](https://docs.rc.fas.harvard.edu/kb/proxy-settings/) guidelines. To prepare for package installation, run the following two commands on RStudio Server before installing any packages. In this example, we want to install package `argparse` as explained by [this link](https://docs.rc.fas.harvard.edu/kb/rstudio-server-vs-rstudio-desktop/#Installing_R_packages_in_RStudio_Server_in_the_FASSE_cluster): 

```shell
Sys.setenv(http_proxy="http://rcproxy.rc.fas.harvard.edu:3128")
Sys.setenv(https_proxy="http://rcproxy.rc.fas.harvard.edu:3128")
install.packages("argparse")
```


If you don't want to install the same R packages over and over again each time you open FASSE, create a \$R_LIBS_USER file. 
[This link](https://docs.rc.fas.harvard.edu/kb/r-packages/) explains some of this, and below are some tips for setting up your \$R_LIBS_USER, but you might want to go to Harvard FAS Research Computing's weekly [office hours](https://www.rc.fas.harvard.edu/training/office-hours/) to get more help.

You'll want to edit your `.bashrc` file (which you can see in your home folder by clicking "View" > "Show Hidden Files") to be the following. 
In this example, the user wants to use R version 4.0.5. `projects`, `ml_r4`, and `ml_rstudio` are examples of Terminal commands that you may to create "aliases" (i.e., shortcuts) for. 
After you do this, you can open a Terminal window (or more than one Terminal window) and type your aliases to, in this example, change the working directory to the `/n/dominici_nsaph_l3/Lab/projects/projects` folder or load RStudio (which requires loading R first).

```shell
# .bashrc

# Source global definitions
if [ -f /etc/bashrc ]; then
. /etc/bashrc
fi

export R_LIBS_USER=$HOME/apps/{your project name}/R_4.0.5:$R_LIBS_USER

# Aliases
alias projects='cd /n/dominici_nsaph_l3/Lab/projects'
alias ml_r4='module load gcc/9.3.0-fasrc01 R/4.0.5-fasrc02'
alias ml_rstudio='module load rstudio/1.1.453-fasrc01'
```

```{note}
If you want to use your \$R_LIBS_USER to access R packages you've installed in previous sessions (as already described above, this allows you to not have to `install.packages()` in RStudio every time you start a FASSE session), you'll need to create a folder, which is called `apps/R_4.0.5` in this example (that is, this example requires a folder called "R_4.0.5" within a folder called "apps"), in your private private home folder.
```
