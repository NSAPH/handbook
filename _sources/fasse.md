# Getting started on FASSE

The following are instructions for logging in to FASSE and setting up your own workspace.

## Prerequisites. Join our project group

1. Get a FASRC account by requesting it [here](https://docs.rc.fas.harvard.edu/kb/get-a-fasse-account-and-project-group/).
2. Join our FASSE project group (please [see steps below](#join-our-fasse-project-group)).
3. Install [Cisco AnyConnect client](https://vpn.rc.fas.harvard.edu/) to connect to the FASRC VPN. 
4. Install 2FA, i.e., Google Authenticator for FASRC. Set it up as explained [here](https://docs.rc.fas.harvard.edu/kb/openauth/).

After creating your FASRC account, follow the steps below to join our FASSE project group:

1. Navigate to the [Add Grants page](https://portal.rc.fas.harvard.edu/request/grants/add) in portal, you will need to login with your FASRC account
2. Expand the plus sign next to “Other”
3. Find the project group you want to be added to: dominici_nsaph
4. Select the checkbox for the project group you want to be added to
You PI will have to approve the addition.  Once you’re notified of the approval, it can take up to an hour for your permissions to be configured.  If you’re not able to access the VPN or your home directory, try waiting an hour and logging in again.

## Step 1. Connect to Harvard's VPN 

1. Type `vpn.rc.fas.harvard.edu` in the Cisco AnyConnect text box (see figures).
2. Type your username in the format `username@fasse`, password and verification code (same as for FASRC).

```{figure} imgs/fasse_vpn.png
---
scale: 60%
align: center 
---
```

```{figure} imgs/fasse_form.png
---
scale: 60%
align: center 
---
```

```{warning}
CMS prohibits accessing data while outside of the U.S., this includes not only opening data files but also 
submitting code/jobs to run on the data. 
```

## Step 2. Access FASSE 

There are a few ways to access FASSE. You can access it via VDI/OoD (in the web browser) by clicking the link here:
https://fasseood.rc.fas.harvard.edu/ 

You can also access it via command line (Terminal) by typing: `ssh username@fasselogin.rc.fas.harvard.edu`. 
To learn more about working in the command line, check out this [Unix Shell tutorial](https://swcarpentry.github.io/shell-novice/).

```{note}
The username, password and verification code are the same as in the previous step 
(and the same as for FASRC).
```

```{tip}
For more information, see the [official documentation](https://docs.rc.fas.harvard.edu/kb/fasse-vdi-apps/).
```

## Step 3. Project workspace

Your **project name** should be informative for the group members and outsiders. 
Think of a **project name** in the following format:

```
<exposure>-<outcome>-<method>
```

- Exposure examples: `pm-components`, `pm-no2`, `pm-no2-o3`, `heat-alert`
- Outcome examples: `cardiovascular`, `respiratory`, `adrd`
- Subpopulation examples: `medicare`, `race`, `ethnicity`
- Method: `reinforcement-learning`, `causalgps` 

For example: `heat_alert-mortality-reinforcement_learning` or shorter `heat_alert-mortality-rl`.

In practice, you may have multiple exposures and outcomes. 
In that case, use your best judgement to name your **project name** based on the guidelines. 
Avoid adding information such as usernames and current date or year.

Create a folder with your **project name** (ie, `heat_alert-mortality-rl`) in the NSAPH workspace here:

```
/n/dominici_nsaph_l3/projects
``` 

```{note}
Make sure to keep your analysis data and code within your folder at `/n/dominici_nsaph_l3/projects`.
```

## Step 4. Create a git repository on GitHub

Navigate to [NSAPH Projects GitHub organization](https://github.com/NSAPH-Projects) in your web browser.
[NSAPH Projects GitHub organization](https://github.com/NSAPH-Projects) is a shared account where all NSAPH members 
can collaborate across many projects at once. If you are not already a member of 
[NSAPH Projects](https://github.com/NSAPH-Projects), ask one of the admins to add you to the organization.

Crete a new git repository under [NSAPH Projects](https://github.com/NSAPH-Projects) and name it with 
your **project name**.

Going forward, make sure to update your GitHub repository daily with your analysis code and documentation.
If you are not familiar with using `git`, check out this [git tutorial](https://swcarpentry.github.io/git-novice/).

````{note}
You should link your GitHub account to the FASSE workspace by typing the commands below in FASSE's command line. 
By doing this, all code contributions (commits) from FASSE will be linked to your GitHub account.

```
git config --global user.name "Mona Lisa"
git config --global user.email "email@example.com"
```
````

## Step 5. Analytic Data

Much of the NSAPH data is already available on FASSE. 
Check out the data catalogue [here](https://nsaph.info/analytic.html).

If you'd like to use any of the analytic datasets, create a symbolic link (symlink) of that dataset instead 
of creating a new copy. A symbolic link is a reference to another file or directory that the 
operating system interprets as a path to that file or directory (a shortcut).

This is how you create a symlink from your `data` folder (in the command line):

```
cd data
ln -s ../analytic/DATA_FOLDER .
```

## Step 6. Setting up R and RStudio

To load R and install packages, follow [these directions](https://docs.rc.fas.harvard.edu/kb/r-packages/). 
If you're using RStudio, you'll need your `R_LIBS_USER` path to set up the interactive session.

In RStudio, if you want to see files outside of your home directory, you can click the three dots 
on the upper right-hand side of the Files window in RStudio (under the refresh arrow) and type 
in the directory path you want. If you want to save files outside your home directory, you can change 
your working directory using the command `setwd([directory path])` in the Console.

```{tip}
If you are using R software in your analysis, have a look at best practices and recommendations 
[here](https://swcarpentry.github.io/r-novice-inflammation/06-best-practices-R/) and 
[here](https://www.nature.com/articles/s41597-022-01143-6#Sec18).
```

## Step 7. Organize your folder

Consider organizing your project folder (and repository) as follows:

```
project-name
├── README.md
├── data/
├── code/
├── figures/
├── reports/
├── results/
└── .gitignore
```

```{tip}
Have a look at the [NSAPH Project Template](https://github.com/NSAPH/project_template). 
Also, here is another template example for new research projects: https://github.com/djnavarro/newproject/
```

Make sure to use the `README.md` and `.gitignore` special files. A `README.md` file is a standard documentation file where you should put information about the content of your 
repository. A `.gitignore` file tells Git which files to ignore when committing your project to the GitHub 
repository. It should be located in the root directory of your repo. Large data file and sensitive data should be 
ignored by Git.

```{warning}
Be careful not to push sensitive data on GitHub. Don't forget that Medicare/Medicaid data should not leave Harvard, 
but your analysis code should be versioned with Git. A `.gitignore` file helps with that.
```

Add path and/or file names of your data in the `.gitignore` file. You can ignore the `data` sub-folder and/or 
all files of a certain format like `.csv`, `.nc` or `.rst`. Add these as new lines in `.gitignore`. For example:

```
data/
*.csv 
*.nc
*.rst
```
