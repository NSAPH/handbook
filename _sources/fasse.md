# FASSE


## Login 


### Prerequisites 

1. Get a FASSE account by requesting it [here](https://docs.rc.fas.harvard.edu/kb/get-a-fasse-account-and-project-group/).
2. Install [Cisco AnyConnect client](https://vpn.rc.fas.harvard.edu/) to connect to the FASRC VPN. 
3. Install 2FA, i.e., Google Authenticator for FASRC. Set it up as explained [here](https://docs.rc.fas.harvard.edu/kb/openauth/).

### VPN login

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

### Access FASSE

1. Open Terminal
2. Type `ssh username@fasselogin.rc.fas.harvard.edu`
3. Type your password and verification code (same as for FASRC, i.e., same as in the previous step)

```{figure} imgs/fasse_ssh.png
---
scale: 70%
align: center 
---
```

To access NSAPH projects folder, type 
```
cd /n/dominici_nsaph_l3/projects
``` 

## Analysis project folder 

### Analytic Data Reuse

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
Even if multiple people read the same analytic files in order to analyze it at the same time, that will not cause problems on FASSE.
```


## RCE Conda

[Steps for setting up a Conda environment](https://github.com/NSAPH/CausalGPS-test/blob/main/Analyses/scaling_synthetic_rce_1/scaling_synthetic_rce.md#steps-for-setting-up-environment)
