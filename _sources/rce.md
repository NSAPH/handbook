# Working on RCE

Unless you are at Harvard and connected to the Harvard network, you will first need to connect to the Harvard's VPN (https://vpn.harvard.edu/) through the Cisco AnyConnect application in order to work on the Research Computing Environment (RCE).

See the official RCE documentation here: https://rce-docs.hmdc.harvard.edu 

```{warning}
The RCE is no longer maintained and the users should plan for their transition to FASSE.
```

## Access RCE

You can access the RCE in the three following ways:

1. In the command line with: `ssh username@rce.hmdc.harvard.edu`
2. In the web browser at: https://rce.hmdc.harvard.edu/nxwebplayer
3. In [the NoMachine software](https://rce-docs.hmdc.harvard.edu/nx4_installation).

## Running RStudio on RCE

Inside the browser or NoMachine interface run the following application: `Menu` -> `Applications` -> `RCE Powered Applications` -> `Anaconda Shell` (see figure below).

```{figure} imgs/img.png
---
scale: 90%
align: center 
---
```

Set the number of CPUs and the memory size for your job. Make sure that the allocated memory exceeds 
the size of the data you want to process. For instance, if your dataset is 20 GB in size, allocate 
40 GB or 60 GB of memory.

```{figure} imgs/job_size.png
---
scale: 30%
align: center 
---
```

When the shell is open, run the following commands to load the NSAPH's R environment and the RStudio.

```bash
export CONDA_ENVS_PATH=/nfs/projects/n/nsaph_common/conda/envs/
export CONDA_PKGS_PATH=/nfs/projects/n/nsaph_common/conda/pkgs/
source activate nsaph
rstudio
```

## RCE Conda environment 

[Steps for setting up a Conda environment](https://github.com/NSAPH/CausalGPS-test/blob/main/Analyses/scaling_synthetic_rce_1/scaling_synthetic_rce.md#steps-for-setting-up-environment)
