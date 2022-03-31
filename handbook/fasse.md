# FASSE


## Account

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
