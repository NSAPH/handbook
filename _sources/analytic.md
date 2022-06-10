# Analytic data

The following data is available at: **`/n/dominici_nsaph_l3/projects/analytic/`**

`````{dropdown} admissions_by_year

```{list-table}
:header-rows: 0

* - data_source
  - MedPar
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

`````{dropdown} denom

```{list-table}
:header-rows: 0

* - data_source
  - MBSF
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


`````{dropdown} qid_yr_exposures

```{list-table}
:header-rows: 0

* - author
  - Daniel Mork
* - rce_location
  - `~/shared_space/ci3_analysis/dmork/Data/DLM_ADRD`
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


`````{dropdown} denom_by_year

```{list-table}
:header-rows: 0

* - rce_location
  - `~/shared_space/ci3_health_data/medicare/mortality/ 1999_2016/wu/cache_data/merged_by_year_v2`
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


`````{dropdown} hospitalization

```{list-table}
:header-rows: 0

* - data_source
  - MedPar derived
* - rce_location
  - `~/shared_space/ci3_analysis/dmork/Data/DLM_ADRD`
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

## Data questions

```{note}
Have a look at the already avaialble analytic data on FASSE. Is the data you want to transfer already there?
```

1. What data sources (MedPar, MBSF, other) were used to create this data file? How many different data sources went into it? 
2. What, if any, processing was done to the data sources? Were there any selections (cuts) done, data quality checks and aggregations? 
3. Was this data used in any publication (add a link)? 
4. Is there any git repository (or subfolder) related to it? (add git location)? 
5. What is the RCE source location? 
6. When was the data created and by who?
7. What is the spatial, temporal resolution? 

