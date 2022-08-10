# Analytic data

```{include} _analytic.md
```

````{warning}
The space of FASSE is limited, so do not copy analytic data to your own folder! Create symlinks to the data in your `data` folder.
Symbolic links (or symlinks) are special files that point to files or directories in other locations on your system.
You will be able to use data with symlinks as normal.

Create the symlink in your `data` folder in the following way:
```
cd data
ln -s /n/dominici_nsaph_l3/projects/analytic/fasse_location .
```
````

```{note}
You need data that is not here, but exists on RCE? 
If so, fill in the form [here](https://gist.github.com/atrisovic/93d379dd84e31f0d63b965de8d529777) to get it transfered to FASSE.
```

## Data questions

1. What data sources (MedPar, MBSF, other) were used to create this data file? How many different data sources went into it? 
2. What, if any, processing was done to the data sources? Were there any selections (cuts) done, data quality checks and aggregations? 
3. Was this data used in any publication (add a link)? 
4. Is there any git repository (or subfolder) related to it? (add git location)? 
5. What is the RCE source location? 
6. When was the data created and by who?
7. What is the spatial, temporal resolution? 

