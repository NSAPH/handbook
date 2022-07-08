# Analytic data

The following data is available at: **`/n/dominici_nsaph_l3/projects/analytic/`**

`````{dropdown} 1. MedPar (Admissions)

```{list-table}
:header-rows: 0

* - data_source
  - MedPar
* - fasse_location
  - `admissions_by_year`
* - rce_location
  - `~/shared_space/ci3_health_data/medicare/gen_admission/ 1999_2016/targeted_conditions/cache_data/admissions_by_year/`
* - date_created
  - Feb 20 2020
* - size
  - 22 GB
* - files
  - 
```
```
   ├── admissions_1999.fst
   ├── admissions_2000.fst
   ├── ...
   └── admissions_2016.fst
```
````{dropdown} header
```
QID                      : chr  
AGE                      : int  
SEX                      : int  
RACE                     : int  
SSA_STATE_CD             : int  
SSA_CNTY_CD              : int  
PROV_NUM                 : int  
ADM_SOURCE               : chr  
ADM_TYPE                 : int  
ADATE                    : chr  
DDATE                    : chr  
BENE_DOD                 : chr  
DODFLAG                  : chr  
ICU_DAY                  : int  
CCI_DAY                  : int  
ICU                      : int  
CCI                      : int  
DIAG1                    : chr  
DIAG2                    : chr  
DIAG3                    : chr  
DIAG4                    : chr  
DIAG5                    : chr  
DIAG6                    : chr  
DIAG7                    : chr  
DIAG8                    : chr  
DIAG9                    : chr  
DIAG10                   : logi 
diag11                   : logi 
diag12                   : logi 
diag13                   : logi 
diag14                   : logi 
diag15                   : logi 
diag16                   : logi 
diag17                   : logi 
diag18                   : logi 
diag19                   : logi 
diag20                   : logi 
diag21                   : logi 
diag22                   : logi 
diag23                   : logi 
diag24                   : logi 
diag25                   : logi 
YEAR                     : int  
LOS                      : int  
Parkinson_pdx            : int  
Parkinson_pdx2dx_10      : int  
Parkinson_pdx2dx_25      : int  
Alzheimer_pdx            : int  
Alzheimer_pdx2dx_10      : int  
Alzheimer_pdx2dx_25      : int  
Dementia_pdx             : int  
Dementia_pdx2dx_10       : int  
Dementia_pdx2dx_25       : int  
CHF_pdx                  : int  
CHF_pdx2dx_10            : int  
CHF_pdx2dx_25            : int  
AMI_pdx                  : int  
AMI_pdx2dx_10            : int  
AMI_pdx2dx_25            : int  
COPD_pdx                 : int  
COPD_pdx2dx_10           : int  
COPD_pdx2dx_25           : int  
DM_pdx                   : int  
DM_pdx2dx_10             : int  
DM_pdx2dx_25             : int  
Stroke_pdx               : int  
Stroke_pdx2dx_10         : int  
Stroke_pdx2dx_25         : int  
CVD_pdx                  : int  
CVD_pdx2dx_10            : int  
CVD_pdx2dx_25            : int  
CSD_pdx                  : int  
CSD_pdx2dx_10            : int  
CSD_pdx2dx_25            : int  
Ischemic_stroke_pdx      : int  
Ischemic_stroke_pdx2dx_10: int  
Ischemic_stroke_pdx2dx_25: int  
Hemo_Stroke_pdx          : int  
Hemo_Stroke_pdx2dx_10    : int  
Hemo_Stroke_pdx2dx_25    : int  
zipcode_R                : int  
Race_gp                  : chr  
Sex_gp                   : chr  
age_gp                   : chr  
Dual                     : int  
```
````
`````

`````{dropdown} 2. MBSF (Denominator) 

```{list-table}
:header-rows: 0

* - data_source
  - MBSF
* - fasse_location
  - `denom`
* - size
  - 7.4 GB
* - files
  - 
```
```
   ├── qid_data_2009.fst
   ├── qid_data_2010.fst
   ├── ...
   ├── qid_data_2016.fst
   ├── qid_entry_exit.fst
   └── year_zip_confounders.fst
```
````{dropdown} header (qid_data_yyyy)
```
qid   : chr  
year  : int  
zip   : int  
sex   : int  
age   : int  
dual  : chr  
dead  : logi 
hmo_mo: chr  
fips  : int  
race  : chr  
sexM  : num  
```
````
````{dropdown} header (year_zip_confounders)
```
zip               : num  
year              : int  
mean_bmi          : num  
smoke_rate        : num  
hispanic          : num  
pct_blk           : num  
medhouseholdincome: num  
medianhousevalue  : num  
poverty           : num  
education         : num  
popdensity        : num  
pct_owner_occ     : num  
summer_tmmx       : num  
winter_tmmx       : num  
summer_rmax       : num  
winter_rmax       : num  
city              : chr  
statecode         : chr  
latitude          : num  
longitude         : num  

min_year: 2000
max_year: 2016
```
````
`````


`````{dropdown} 3. Annual Exposure per Medicare Beneficiary

```{list-table}
:header-rows: 0

* - rce_location
  - `~/shared_space/ci3_analysis/dmork/Data/DLM_ADRD`
* - fasse_location
  - `qid_yr_exposures`
* - dataset_author
  - Daniel Mork
* - date_created
  - April 2022
* - size
  - 139 GB
* - description
  - Annual exposure measurements (columns, 2000-2016) for each Medicare benficiary (rows) tied to their zip code of residence in a given year. Exposures (xxx in file name) include: no2, ozone, pm2.5, pm2.5components, pr (precipitation), rmax (max humidity), tmmx (max temperature), zip (zip code of residence).
* - files
  - 
```

```
    ├── qid_yr_no2.fst
    ├── qid_yr_ozone.fst
    ├── qid_yr_pm25comp_br.fst
    ├── qid_yr_pm25comp_ca.fst
    ├── qid_yr_pm25comp_cu.fst
    ├── qid_yr_pm25comp_ec.fst
    ├── qid_yr_pm25comp_fe.fst
    ├── qid_yr_pm25comp_k.fst
    ├── qid_yr_pm25comp_nh4.fst
    ├── qid_yr_pm25comp_ni.fst
    ├── qid_yr_pm25comp_no3.fst
    ├── qid_yr_pm25comp_oc.fst
    ├── qid_yr_pm25comp_pb.fst
    ├── qid_yr_pm25comp_si.fst
    ├── qid_yr_pm25comp_so4.fst
    ├── qid_yr_pm25comp_v.fst
    ├── qid_yr_pm25comp_z.fst
    ├── qid_yr_pm25.fst
    ├── qid_yr_pr.fst
    ├── qid_yr_rmax.fst
    ├── qid_yr_tmmx.fst
    └── qid_yr_zip.fst
```

````{dropdown} header (qid_yr_xxx.fst):
```
qid : chr  
2000: num  
2001: num  
2002: num  
2003: num  
2004: num  
2005: num  
2006: num  
2007: num  
2008: num  
2009: num  
2010: num  
2011: num  
2012: num  
2013: num  
2014: num  
2015: num  
2016: num
```
````
`````


`````{dropdown} 4. MBSF (Enrollment file, denominator) 

```{list-table}
:header-rows: 0

* - data_source
  - MBSF, census (interpolated), BRFSS (interpolated), PM2.5 exposure, seasonal temperature
* - rce_location
  - `~/shared_space/ci3_health_data/medicare/mortality/ 1999_2016/wu/cache_data/merged_by_year_v2`
* - fasse_location
  - `denom_by_year`
* - GitHub 
  - [github.com/NSAPH/National-Causal-Analysis](https://github.com/NSAPH/National-Causal-Analysis/tree/master/MergedData)
* - dataset_author
  - Ben Sabath, Xiao Wu
* - spatial_resolution
  - zipcode
* - temporal_coverage
  - 1999-2016
* - processing_description
  - Recommended for use. Available in both `.fst` and `.csv` formats on FASSE.
* - date_created
  - Apr 2021
* - size
  - 7.4 GB
* - files
  - 
```

```
   ├── confounder_exposure_merged_nodups_health_1999.fst
   ├── ...
   └── confounder_exposure_merged_nodups_health_2016.fst
```
````{dropdown} header
```
zip                         : int  
year                        : int  
qid                         : chr  
dodflag                     : chr  
bene_dod                    : chr  
sex                         : int  
race                        : int  
age                         : int  
hmo_mo                      : chr  
hmoind                      : chr  
statecode                   : chr  
latitude                    : num  
longitude                   : num  
dual                        : chr  
death                       : int  
dead                        : logi 
entry_age                   : int  
entry_year                  : int  
entry_age_break             : int  
followup_year               : num  
followup_year_plus_one      : num  
pm25_ensemble               : num  
pm25_no_interp              : num  
pm25_nn                     : num  
ozone                       : num  
ozone_no_interp             : num  
zcta                        : int  
poverty                     : num  
popdensity                  : num  
medianhousevalue            : num  
pct_blk                     : num  
medhouseholdincome          : num  
pct_owner_occ               : num  
hispanic                    : num  
education                   : num  
population                  : num  
zcta_no_interp              : int  
poverty_no_interp           : num  
popdensity_no_interp        : num  
medianhousevalue_no_interp  : num  
pct_blk_no_interp           : num  
medhouseholdincome_no_interp: num  
pct_owner_occ_no_interp     : num  
hispanic_no_interp          : num  
education_no_interp         : num  
population_no_interp        : int  
smoke_rate                  : num  
mean_bmi                    : num  
smoke_rate_no_interp        : num  
mean_bmi_no_interp          : num  
amb_visit_pct               : num  
a1c_exm_pct                 : num  
amb_visit_pct_no_interp     : num  
a1c_exm_pct_no_interp       : num  
tmmx                        : num  
rmax                        : num  
pr                          : num  
cluster_cat                 : chr  
fips_no_interp              : int  
fips                        : int  
summer_tmmx                 : num  
summer_rmax                 : num  
winter_tmmx                 : num  
winter_rmax                 : num  
```
````
`````


`````{dropdown} 5. AD/ADRD Hospitalization

```{list-table}
:header-rows: 0

* - data_source
  - MedPar derived
* - rce_location
  - `~/shared_space/ci3_analysis/dmork/Data/DLM_ADRD`
* - fasse_location
  - `hospitalization`
* - size
  - 1.2 GB
* - files
  - 
```
```
   ├── First_hosp_AD_any.fst
   ├── First_hosp_AD_primary.fst
   ├── First_hosp_ADRD_any.fst
   ├── First_hosp_ADRD_primary.fst
   ├── First_hosp_ADRD_secondary.fst
   └── First_hosp_AD_secondary.fst
```
````{dropdown} header
```
QID  : Factor 
ADATE: Date
year : num  
```
````
`````


`````{dropdown} 6. Medicare Entry Age

```{list-table}
:header-rows: 0

* - data_source
  - MBSF derived
* - rce_location
  - `/nfs/nsaph_ci3/scratch/jan2021_whanhee_cache/entry_age/`
* - fasse_location
  - `medicare_entry_age`
* - size
  - 2.3 GB
* - date_created
  - Jan 26, 2021
* - dataset_author
  - Ben Sabath, Whenhee Lee
* - spatial_resolution
  - zipcode
* - git_repository
  - [NSAPH/data_requests](https://github.com/NSAPH/data_requests/blob/master/request_projects/jan2021_whanhee_fisrt_hosps/code/1_create_indivdual_vars.R)
* - files
  -
```
```
   └── medicare_entry_age.csv
```
`````

`````{dropdown} 7. Years in Medicare 
```{list-table}
:header-rows: 0

* - data_source
  - MBSF derived
* - rce_location
  - `/nfs/nsaph_ci3/scratch/jan2021_whanhee_cache/follow_up/`
* - fasse_location
  - `years_in_medicare`
* - description
  - Number of years a beneficiary has been in Medicare (or in other words, the number of years since one has entered Medicare). Allows for grouping on how long beneficiaries have been in Medicare.
* - size
  - 8.8 GB
* - date_created
  - Jan 26, 2021
* - temporal_coverage
  - 1999-2016
* - dataset_author
  - Ben Sabath, Whanhee Lee
* - spatial_resolution
  - zipcode
* - git_repository
  - [NSAPH/data_requests](https://github.com/NSAPH/data_requests/blob/master/request_projects/jan2021_whanhee_fisrt_hosps/code/1_create_indivdual_vars.R)
* - files
  -
```
```
   ├── follow_up_year_2000.fst
   ├── ...
   └── follow_up_year_2016.fst
```
`````

`````{dropdown} 8. Temperature Humidity Precipitation 
```{list-table}
:header-rows: 0
* - rce_location
  - `/nfs/nsaph_ci3/ci3_confounders/data_for_analysis/earth_engine/ temperature/temperature_seasonal_zipcode_combined.csv`
* - fasse_location
  - `temperature_seasonal_zipcode`
* - dataset_author
  - Xiao Wi, Ben Sabath
* - date_created
  - Jul 23,  2020
* - data_source
   - Google Earth Engine provides a single interface for interacting with a number of geospatial data sources. The sources used and links to their documentation are: [GRIDMET](https://developers.google.com/earth-engine/datasets/catalog/IDAHO_EPSCOR_GRIDMET), [NLDAS](https://developers.google.com/earth-engine/datasets/catalog/NASA_NLDAS_FORA0125_H002), [MODIS MOD10A1.006](https://developers.google.com/earth-engine/datasets/catalog/MODIS_006_MOD10A1), [GLDAS](https://developers.google.com/earth-engine/datasets/catalog/NASA_GLDAS_V021_NOAH_G025_T3H), [NOAA CDR PATMOSX](https://developers.google.com/earth-engine/datasets/catalog/NOAA_CDR_PATMOSX_V53), [NOAA NCEP Climate Forecast System V2](https://developers.google.com/earth-engine/datasets/catalog/NOAA_CFSV2_FOR6H)
* - spatial_coverage
  - contiguous US
* - spatial_resolution
  - zipcode
* - temporal_coverage
  - 1999-2019
* - temporal resolution
  - annually
* - description
  - This dataset contains information on temperature, relative humidity, and total precipitation data. The data is available as raster files on Google earth engine. The temporal and spatial resolutions varied by data source, but all were available at a daily resolution or more frequently. Where the time resolution of the rasters is more than daily, daily averages for each raster were calculated. Next, using Google earth engine's spatial averaging algorithms and a set of polygons representing the areas of interest, the daily value for each polygon was calculated. The polygons used were the ones described in the preceding section. The results of this calculation were then downloaded as a csv file to the RCE. At this point, there is one file for each year. Following this, annual averages are calculated for each location, and these are combined in to a single file. The daily values are also combined in to a single file. For the `combined_zips` files (which combine the zip code polygon based measures with the the point based estimates to address zip codes without area) there is an additional step. Values for zip codes not in the polygon based measure are taken from the point based measures to address the ~7000 zip codes without area that are missing from the polygon shape file.
* - GitHub 
  - [NSAPH/data_documentation](https://github.com/NSAPH/data_documentation/blob/master/earth_engine_docs/earth_engine_data.Rmd)
* - meterological
  - Temperature (K) - variable name: tmmx (Source: GRIDMET); Relative Humidity - variable name: rmax (Source: GRIDMET)
* - size
  - 65 MB
* - header 
  - `ZIP,year,summer_tmmx,summer_rmax,winter_tmmx,winter_rmax`
* - files
  -
```
```
   └── temperature_seasonal_zipcode_combined.csv
```
`````

`````{dropdown} 9.  Pollution-Census-Temperature covariates
```{list-table}
:header-rows: 0
* - data_source
  - US Census/ACS, Business Analyst Data Set, BRFSS
* - rce_location
  - `/nfs/nsaph_ci3/ci3_health_data/medicare/ mortality/1999_2016/wu/output_data /merged_covariates.csv`
* - fasse_location
  - `merged_covariates_pm_census_temp`
* - dataset_author
  - Xiao Wi, Ben Sabath
* - date_created
  - May 29, 2019
* - spatial_coverage
  - contiguous US
* - spatial_resolution
  - zipcode
* - temporal_coverage
  - 2000-2016
* - temporal resolution
  - annually
* - publication 
  - https://www.science.org/doi/10.1126/sciadv.aba5692
* - GitHub 
  - [nejm_confounder_summary/nejm_confounder](https://github.com/NSAPH/data_documentation/blob/master/nejm_confounder_summary/nejm_confounders.csv) and [rce_data_list/confounder_data](https://github.com/NSAPH/data_documentation/blob/master/rce_data_list/confounder_data.csv)
* - size
  - 296 MB
* - header 
  - `zip, year, pm25_ensemble, pm25_no_interp, pm25_nn, ozone, ozone_no_interp, zcta, poverty, popdensity, medianhousevalue, pct_blk, medhouseholdincome, pct_owner_occ, hispanic, education, population, zcta_no_interp, poverty_no_interp, popdensity_no_interp, medianhousevalue_no_interp, pct_blk_no_interp, medhouseholdincome_no_interp, pct_owner_occ_no_interp, hispanic_no_interp, education_no_interp, population_no_interp, smoke_rate, mean_bmi, smoke_rate_no_interp, mean_bmi_no_interp, amb_visit_pct, a1c_exm_pct, amb_visit_pct_no_interp, a1c_exm_pct_no_interp, tmmx, rmax, pr, cluster_cat, fips, fips_no_interp`
* - files
  - 
```
```
   └── merged_covariates.csv
```
`````

`````{dropdown} 10.  Medicaid - Children
```{list-table}
:header-rows: 0
* - data_source
  - Medicaid
* - rce_location
  - `/nfs/nsaph_ci3/ci3_health_data/medicaid/respiratory /1999_2012/youth_resp_hosps_jlee/data`
* - fasse_location
  - `medicaid_children_99-12`
* - dataset_author
  - Jenny Lee
* - date_created
  - 2021
* - spatial_coverage
  - contiguous US
* - spatial_resolution
  - zipcode
* - temporal_coverage
  - 1999-2012
* - temporal resolution
  - annually
* - processing_description
  - The data prepared for this project consists of the Medicaid Fee For Service population, with unrestricted Medicaid benefits, under the age of 20 from 1999-2012. This data also includes all hospitalizations for that population, with indicators included regarding whether or not they were associated with a set of respiratory hospitalizations. See the schema for the hospitalization data below for details on specific indicators.
* - GitHub 
  - [NSAPH/data_requests](https://github.com/NSAPH/data_requests/tree/master/request_projects/feb2021_jenny_medicaid_resp)
* - exposures
  - Xiao Wu's CausalGPS PM2.5 data 
* - size
  - 14 GB
* - files
  -
``` 
```
├── denom
│   ├── denom_under_20_1999.fst
│   ├── ...
│   └── denom_under_20_2012.fst
└── hosps
    ├── under_20_admissions_1999.fst
    ├── ...
    └── under_20_admissions_2012.fst
```
`````

`````{dropdown} 11.  Exposure-census-BRFFS confounders
```{list-table}
:header-rows: 0
* - data_source
  - US Census, BRFSS
* - rce_location
  - `/nfs/nsaph_ci3/scratch/jan2021_whanhee_cache/cache_dir/ merged_exposure_confounders/`
* - fasse_location
  - `confounders`
* - dataset_author
  - Ben Sabath, Whanhee Lee
* - date_created
  - Apr 23, 2021
* - spatial_coverage
  - contiguous US
* - spatial_resolution
  - zipcode, zcta
* - temporal_coverage
  - 2000-2016
* - temporal resolution
  - annually
* - GitHub
  - [data_requests](https://github.com/NSAPH/data_requests/blob/master/request_projects/jan2021_whanhee_fisrt_hosps/code/6_join_exposure_to_confounders.R)
* - size
  - 247 MB
* - header 
  - `ZIP, year, zcta, poverty, popdensity, medianhousevalue, pct_blk, medhouseholdincome, pct_owner_occ, hispanic, education, population, pct_asian, pct_native, pct_white, smoke_rate, mean_bmi, pm25.current_year, ozone.current_year, no2.current_year, ozone_summer.current_year, pm25.one_year_lag, ozone.one_year_lag, no2.one_year_lag, ozone_summer.one_year_lag`
* - files
  - 
```
```
   ├── merged_confounders_2000.csv
   ├── ...
   └── merged_confounders_2016.csv
```
`````

`````{dropdown} 12.  ZIP to ZCTA crosswalk (2015)
```{list-table}
:header-rows: 0
* - rce_location
  - `~/shared_space/ci3_exposure/locations/zcta/crosswalk/`
* - fasse_location
  - `zip_to_zcta`
* - date_created
  - Nov 2, 2015
* - spatial_coverage
  - contiguous US
* - size
  - 1.8 MB
* - header 
  - `ZIP,PO_NAME,STATE,ZIP_TYPE,ZCTA`
* - files
  - 
```
```
   └── Zip_to_ZCTA_crosswalk_2015_JSI.csv
```
`````


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

