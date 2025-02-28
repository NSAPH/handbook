# Getting started on CANNON

The following are instructions for logging in to CANNON and setting up your own workspace.

## Prerequisites. Join our project group

1. Get a FASRC account by requesting it [here](https://docs.rc.fas.harvard.edu/kb/get-a-fasse-account-and-project-group/).
2. Navigate to the [Add Grants page](https://portal.rc.fas.harvard.edu/request/grants/add) in portal, you will need to login with your FASRC account
3. Expand the plus sign next to “Other”
4. Find the project group you want to be added to: `dominici_lab` (`dominici_nsaph` is for FASSE).
5. Select the checkbox for the project group you want to be added to 

Your PI will have to approve the addition.  Once you’re notified of the approval, it can take up to an hour for your permissions to be configured.  If you’re not able to access the VPN or your home directory, try waiting an hour and logging in again.

## Step 1. Connect to Harvard's VPN 

Install [Cisco AnyConnect client](https://vpn.rc.fas.harvard.edu/) to connect to the FASRC VPN. 
Install 2FA, i.e., Google Authenticator for FASRC. Set it up as explained [here](https://docs.rc.fas.harvard.edu/kb/openauth/).

1. Type `vpn.rc.fas.harvard.edu` in the Cisco AnyConnect text box (see figures).
2. Type your username in the format `username@fasrc`, password and verification code (same as for FASRC).

```{figure} imgs/fasse_vpn.png
---
scale: 60%
align: center 
---
```

```{figure} imgs/cannon_form.png
---
scale: 60%
align: center 
---
```

```{warning}
Cannon is the Faculty of Arts and Sciences research computing cluster for users with Data Security Level 2 data. If you have Data Security Level 3 data, you must use the FAS Secure Environment (FASSE) cluster. 
```

## Step 2. Access CANNON 

There are a few ways to access CANNON. You can access it via VDI/OoD (in the web browser) by clicking the link here:
https://vdi.rc.fas.harvard.edu 

You can also access it via command line (Terminal) by typing: `ssh username@login.rc.fas.harvard.edu`. 
To learn more about working in the command line, check out this [Unix Shell tutorial](https://swcarpentry.github.io/shell-novice/).

```{note}
The username, password and verification code are the same as in the previous step 
(and the same as for FASRC).
```

```{tip}
For more information, see the [official documentation](https://docs.rc.fas.harvard.edu/kb/iqss-cannon-quickstart-guide/).
```

## Step 3. Project workspace

Your **project name** should be informative for the group members and outsiders. 
Think of a **project name** in the following format:

```
<exposure>-<outcome>-<method>
```

- Exposure examples: `pm-components`, `pm-no2`, `pm-no2-o3`, `heat-alert`
- Outcome examples: `cardiovascular`, `respiratory`, `adrd`
- Method: `reinforcement-learning`, `causalgps` 

For example: `heat_alert-mortality-reinforcement_learning` or shorter `heat_alert-mortality-rl`.

In practice, you may have multiple exposures and outcomes. 
In that case, use your best judgement for your **project name** based on the guidelines. 
Avoid adding information such as usernames and current date or year.

Next, you should create a folder with your **project name** in the NSAPH projects folder at `/n/dominici_lab/lab/projects`.
You can do that by opening "File System" in FAS-RC Remote Desktop and navigating to the projects folder (see Fig.).

```{figure} imgs/cannon_folder.png
---
scale: 80%
align: center 
---
```

Create there a new folder with your **project name** (ie, `heat_alert-mortality-rl`).

```{note}
Use your **project name** folder in `/n/dominici_lab/lab/projects` as a workspace 
for your analysis data and code. 
```