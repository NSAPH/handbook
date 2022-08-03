# Data sources

| Medical                                                 | Description |
|---------------------------------------------------------| ----------- |
| [MedPar data](https://resdac.org/cms-data/files/medpar) | Includes hospitalizations for FFS individuals (1999-2017) | 
| [MBSF](https://resdac.org/cms-data/files/mbsf-base)     | The enrollment file and also has mortality for everyone (1999-2017) | 
| MCBS                                                    | Survey for sample of all Medicare or just FFS (1999-2004, 2007-2013, 2015-2017) |

## Heath data references

- RESDAC [Using Medicare Hospitalization Information and the MedPAR]("http://resdac.umn.edu/sites/resdac.umn.edu/files/Using%20Medicare%20Hospitalization%20Information%20and%20the%20MedPAR%20(Slides).pdf") 
- [Coverage Denials](https://www.healthaffairs.org/doi/pdf/10.1377/hlthaff.2021.01054?casa_token=mwc33u4-yscAAAAA:E5OXpiodc6LWCqMSdqt_7bfFj-zlhi9IVq3-8IJSg7cA_xTpDuF1CvANoBMHbk_18JqI9uPU0g)
- RESDAC Online learning: https://resdac.org/online-learning
- RESDAC Learning and workshops: https://resdac.org/learn

## PM 2.5 Components

`````{dropdown} PM 2.5 component data

```{list-table}
:header-rows: 0

* - spatial_coverage
  - US
* - spatial_resolution
  - zipcode
* - temporal_coverage
  - 2000-2019
* - temporal_resolution
  - annually
* - size
  - 251 MG
* - processing_description
  - These are annual estimations of PM2.5 speciations at ZIP Code-level  across the contiguous US, aggregated from Heresh's grid-level estimations. For a general ZIP Code, which has normal street delivery route and therefore can be represented by a polygonal area, we estimate the ZIP Code-level PM2.5 by averaging the predictions of grid cells whose centroids lie inside the polygon of that ZIP Code; for other ZIP Codes that do not have polygon representations, for example an apartment building, a military base, or a post office, we consider them as single points and estimate their ZIP Code-level PM2.5 by linking the prediction of the nearest grid cell. For ec, oc, nh4, no3, and so4 the units are microgram per cubic meter; for br, ca, cu, fe, k, ni, pb, si, v, and z the units are nanogram per cubic meter.
* - fasse_location
  - `/n/dominici_nsaph_l3/data/pm25_components`
* - git_repository
  - https://github.com/yycome/PM25_Components
* - publication 
  - Amini, H., M. Danesh-Yazdi, Q. Di, W. Requia, Y. Wei, Y. Abu Awad, L. Shi, M. Franklin, C.-M. Kang, J. M. Wolfson, P. James, R. Habre, Q. Zhu, J. S. Apte, Z. J. Andersen, X. Xing, C. Hultquist, I. Kloog, F. Dominici, P. Koutrakis, J. Schwartz. 2022. Annual Mean PM2.5Components (EC, NH4, NO3, OC, SO4) 50m Urban and 1km Non-Urban Area Grids for Contiguous U.S., 2000-2019 v1. (Preliminary Release). Palisades, NY: NASA Socioeconomic Data and Applications Center (SEDAC). https://doi.org/10.7927/7wj3-en73
* - dataset_author
  - weiyg@hsph.harvard.edu
* - header 
  - `ZIP, br, ca, cu, ec, fe, k, nh4, ni, no3, oc, pb, si, so4, v, z`
* - files
  -
```
```
   ├── 2000.csv
   ├── ...
   └── 2019.csv
```
`````

## Commonly Used Public Data Sources

- [CMS Synthetic data: 2008, 2009, and 2010](https://www.cms.gov/Research-Statistics-Data-and-Systems/Downloadable-Public-Use-Files/SynPUFs/DE_Syn_PUF)
- [CDC, Behavioral Risk Factor Surveillance System (BRFSS) data for body mass index and smoking status](https://www.cdc.gov/brfss/annual_data/annual_2008.htm)
- [PM2.5 concentrations (US) from Di et al. 2019](https://beta.sedac.ciesin.columbia.edu/data/set/aqdh-pm2-5-concentrations-contiguous-us-1-km-2000-2016)
- [Census data](https://www.census.gov/data/developers/data-sets/acs-5year.2010.html)
- [GridMET data](https://www.climatologylab.org/gridmet.html)

## Common Acronyms


```{glossary}
FFS
  fee-for-service

MCBS
  Medicare Current Beneficiary Summary

MBSF
  Master Beneficiary Summary File

MEDPAR
  Medicare Provider Analysis and Review
```
