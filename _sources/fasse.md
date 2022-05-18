# FASSE Setup

The following are instruction for logging in to FASSE and setting up your own workspace.

## Prerequisites 

1. Get a FASRC account by requesting it [here](https://docs.rc.fas.harvard.edu/kb/get-a-fasse-account-and-project-group/).
2. Join our FASSE project group (please see steps below).
3. Install [Cisco AnyConnect client](https://vpn.rc.fas.harvard.edu/) to connect to the FASRC VPN. 
4. Install 2FA, i.e., Google Authenticator for FASRC. Set it up as explained [here](https://docs.rc.fas.harvard.edu/kb/openauth/).

## Join our FASSE project group
After creating your FASRC account, follow the steps below to join our FASSE project group:
1. Navigate to the [Add Grants page](https://portal.rc.fas.harvard.edu/request/grants/add) in portal, you will need to login with your FASRC account
2. Expand the plus sign next to “Other”
3. Find the project group you want to be added to: dominici_nsaph
4. Select the checkbox for the project group you want to be added to
You PI will have to approve the addition.  Once you’re notified of the approval, it can take up to an hour for your permissions to be configured.  If you’re not able to access the VPN or your home directory, try waiting an hour and logging in again.

## VPN login

1. Type `vpn.rc.fas.harvard.edu` in the Cisco AnyConnect text box (see figures).
2. Type your username in the format `username@fasse`, password and verification code (same as for FASRC).

```{figure} imgs/fasse_vpn.png
---
scale: 70%
align: center 
---
```

```{figure} imgs/fasse_form.png
---
scale: 70%
align: center 
---
```

```{warning}
CMS prohibits accessing data while outside of the US, this includes not only opening data files but also submitting code/jobs to run on the data. This also means no jobs will be allowed to be run on RCE/FASSE outside the U.S. While Harvard does not restrict cluster access, we are not allowed to access it per the DUA with CMS. For people not using CMS data, we encourage you to work on FASRC.
```

## Access FASSE via command line

1. Open Terminal
2. Type `ssh username@fasselogin.rc.fas.harvard.edu`
3. Type your password and verification code (same as for FASRC, i.e., same as in the previous step)

```{figure} imgs/fasse_ssh.png
---
scale: 70%
align: center 
---
```

## Access FASSE via VDI/OoD (in browser)

Acess FASSE via the web browser here: https://fasseood.rc.fas.harvard.edu/ 

See the official documentation here: https://docs.rc.fas.harvard.edu/kb/fasse-vdi-apps/

## Analysis project folder 

We strongly encourage users to keep their analysis data and code in the NSAPH shared project space here:

```
cd /n/dominici_nsaph_l3/projects
``` 

Create a subfolder and GitHub repository for your analysis by following the convention [here](naming-convention).

## Link your FASSE account to GitHub

Create a GitHub repository for your analysis.

```{note}
To clone an existing GitHub repository or push to GitHub, you may need to create a GitHub token. See instructions for that [here](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token).
```

Link your GitHub account to the FASSE workspace by setting your git username and email. By doing this, all code contributions (commits) from FASSE will be linked to your GitHub account.

```
git config --global user.name "Mona Lisa"
git config --global user.email "email@example.com"
```

## Analytic Data Reuse

If you are using any of the pre-processed analytic datasets, create a symbolic link (symlink) of that dataset instead of creating a new copy. A symbolic link is essentially a reference to another file or directory that the operating system interprets as a path to that file or directory (a shortcut).

This is how you create a symlink:

```
# ln -s source_file symbolic_link
ln -s ../analytic/my_file.txt my_link.txt

# to verify if the symlink was successfully created, run:
ls -l my_link.txt

# symlink to a directory
ln -s ../analytic/medpar /data/medpar
```

```{note}
Even if multiple people read the same analytic files at the same time, that will not cause problems on FASSE.
```

## Setting up R and RStudio on FASSE

To load R and install packages, follow [these directions](https://docs.rc.fas.harvard.edu/kb/r-packages/). If you're using RStudio, you'll need your R_LIBS_USER path to set up the interactive session.

In RStudio, if you want to see files outside of your home directory, you can click the three dots on the upper right-hand side of the Files window in RStudio (under the refresh arrow) and type in the directory path you want. If you want to save files outside your home directory, you can change your working directory using the command "setwd([directory path])" in the Console.

## Terminal settings (optional)

Consider adding the following lines in your `~/.bash_profile` file to set shortcuts (aliases) and have more colorful working environment.

```sh
# function to see active git branch
parse_git_branch() {
     git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/'
}

# Aliases 
alias projects='cd /n/dominici_nsaph_l3/projects' 

# Prompt colors
PS1="\[\033[01;32m\]\u@\h\[\033[0;00m\]:\[\033[01;36m\]\w\[\033[35m\]\$(parse_git_branch)\[\033[00m\] $ "
```

The prompt colors are encoded in `\[\033[COLORm\]`. You can modify the number to change the prompt color. Here are the values for different text colors:

| Black: 30 | Blue: 34 |
| --------- | -------- |
| Cyan: 36 | Green: 32 |
| Purple: 35 | Red: 31 |
| White: 37 | Yellow: 33 |

Source your `.bash_profile` file to see the changes:

```sh
. ~/.bash_profile
```
The new prompt look:

```{figure} imgs/fasse_cmd.png
---
scale: 80%
align: center 
---
```

## RCE Conda

[Steps for setting up a Conda environment](https://github.com/NSAPH/CausalGPS-test/blob/main/Analyses/scaling_synthetic_rce_1/scaling_synthetic_rce.md#steps-for-setting-up-environment)
