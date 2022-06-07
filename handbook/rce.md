# Work on Research Computing Environment (RCE)

To work on RCE, you also need to connect to the Harvard's VPN (https://vpn.harvard.edu/) through the Cisco AnyConnect.

See the official documentation here: https://rce-docs.hmdc.harvard.edu 

```{warning}
RCE is no longer maintained and the users should plan for their transition to FASSE.
```

## Access RCE

You can access the RCE in the three following ways:

1. In the command line with: `ssh username@rce.hmdc.harvard.edu`
2. In the web browser at: https://rce.hmdc.harvard.edu/nxwebplayer
3. In the [NoMachine](https://rce-docs.hmdc.harvard.edu/nx4_installation) software.

## Running RStudio on RCE

Inside the browser or NoMachine interface run the following application: `Menu` -> `Applications` -> `Anaconda Shell` (see figure below).

```{figure} imgs/img.png
---
scale: 70%
align: center 
---
```

When the shell is open, run the following commands to load the R NSAPH environment and RStudio.

```bash
export CONDA_ENVS_PATH=/nfs/projects/n/nsaph_common/conda/envs/
export CONDA_PKGS_PATH=/nfs/projects/n/nsaph_common/conda/pkgs/
source activate nsaph
rstudio
```

## RCE Conda environment 

[Steps for setting up a Conda environment](https://github.com/NSAPH/CausalGPS-test/blob/main/Analyses/scaling_synthetic_rce_1/scaling_synthetic_rce.md#steps-for-setting-up-environment)
