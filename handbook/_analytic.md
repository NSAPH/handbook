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
* - dataset_author
  - Daniel Mork
* - description
  - The first recorded hospitalization for each individual broken down by primary/secondary/any billing code (ICD).
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
* - temporal_resolution
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
* - temporal_resolution
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
* - temporal_resolution
  - annually
* - description
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
* - temporal_resolution
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

`````{dropdown} 13. ADRD Hospitalization Records
```{list-table}
:header-rows: 0
* - dataset_author
  - Shuxin Dong
* - date_created
  - Jan 27, 2022
* - data_source
  - MedPar (admissions)
* - spatial_coverage
  - US
* - spatial_resolution
  - zipcode (unaggregated)
* - temporal_coverage
  - 2000-2016
* - temporal_resolution
  - daily (with admission date)
* - description
  - extract the ADRD hospitalizations based on the Chronic Condition Warehouse
* - rce_location
  - `~/shared_space/ci3_analysis/ data_ADRDhospitalization/ ADRDhospitalization_CCWlist/`
* - fasse_location
  - `adrd_hospitalization`
* - size
  - 1.9 GB
* - GitHub
  - https://github.com/ShuxinD/ADRDdata
* - other
  - The Chronic Condition Warehouse list for ADRD: https://www2.ccwdata.org/web/guest/condition-categories
* - files
  -
```
```
   ├── ADRD_2000.fst
   ├── ...
   └── ADRD_2016.fst
```
````{dropdown} header
```
QID           : chr 
ADATE         : Date
DDATE         : Date
zipcode_R     : int 
DIAG1         : chr 
DIAG2         : chr 
DIAG3         : chr 
DIAG4         : chr 
DIAG5         : chr 
DIAG6         : chr 
DIAG7         : chr 
DIAG8         : chr 
DIAG9         : chr 
DIAG10        : chr 
AGE           : int 
Sex_gp        : chr 
Race_gp       : chr 
SSA_STATE_CD  : int 
SSA_CNTY_CD   : int 
PROV_NUM      : int 
ADM_SOURCE    : chr 
ADM_TYPE      : int 
Dual          : int 
year          : num 
AD_primary    : logi
AD_any        : logi
AD_secondary  : logi
ADRD_primary  : logi
ADRD_any      : logi
ADRD_secondary: logi
```
````
`````

`````{dropdown} 14. Medpar File 2000-2016 Clean 
```{list-table}
:header-rows: 0
* - dataset_author
  - Mahdieh Danesh Yazdi
* - date_created
  - May 2019
* - data_source
  - MedPar (admissions)
* - spatial_coverage
  - US
* - size
  - 1.8 GB
* - spatial_resolution
  - zipcode, city
* - temporal_coverage
  - 2000-2016
* - temporal_resolution
  - admissions date
* - processing_description
  - The data was limited to the years 2000-2016 (1999 was dropped). Demographic data was removed (use demographic data from denominator file). Duplicated admission records were removed. For multiple admissions on the same day, the longer length of stay was kept and those without missing diagnositic codes. Subset data to keep only first two diagnostic codes. A diabetes varible was created (would review ICD codes used clinically prior to use). 
* - rce_location
  - `~/shared_space/ci3_mdaneshyazdi/Medpar_Data/ data/medpar_hospital_clean_0619.rds`
* - fasse_location
  - `medpar_hospital_clean_0619`
* - files
  -
```
```
   └── medpar_hospital_clean_0619.rds
```
`````

`````{dropdown} 15. Denominator File 2000-2016 Clean 
```{list-table}
:header-rows: 0
* - dataset_author
  - Mahdieh Danesh Yazdi
* - date_created
  - May 2019
* - data_source
  - MBSF (denominator)
* - spatial_coverage
  - US
* - size
  - 3.8 GB
* - spatial_resolution
  - zipcode
* - temporal_coverage
  - 2000-2016
* - temporal_resolution
  - annually
* - processing_description
  - The data was limited to the years 2000-2016 (1999 was dropped). Rows with empty or missing QID values were dropped. Those whose sex changed through follow up were dropped. Those whose race changed through follow up were assigned "Other/Unknown" category. Those who had multiple dates of death in different years were dropped. For those with multiple dates of death in the same year, earlier date of death was assigned. If duplicate rows existed, one with date of death and one without, the row with non-missing date of death was kept. Multiple QID-year rows with differing values of other variables were removed. Observations with invalid zip codes were removed. Warning: There may be excess deaths on the last day of the month due to CMS processing. Sometimes when the exact date of death is unknown, it is assigned to the last day of the month.
* - rce_location
  - `~/shared_space/ci3_mdaneshyazdi/Denominator_Data/ data/denominator_clean_0619.rds`
* - fasse_location
  - `denominator_clean_0619`
* - files
  -
```
```
   └── denominator_clean_0619.rds
```
`````

`````{dropdown} 16. Denominator Clean Merged with Exposure and Covariate Data 
```{list-table}
:header-rows: 0
* - dataset_author
  - Mahdieh Danesh Yazdi
* - date_created
  - February 2020
* - data_source
  - MedPar (admissions), MBSF (denominator)
* - spatial_coverage
  - US
* - size
  - 30 GB (`fst`) and 4.4 GB (`rds`)
* - spatial_resolution
  - zipcode
* - temporal_coverage
  - 2000-2016
* - temporal_resolution
  -  annually
* - processing_description
  - The clean denominator file merged with annual PM2.5, NO2, O3 levels from 1-km exposure models generated by Qian Di and Weeberb Requia aggregatetd to zip code level by Yaguang Wei. Also merged with covariate data from the Census, ACS, BRFSS, and Dartmouth Health Atlas created by Ben Sabath. Missing values were filled in using interpolated/extrapolated values from Liuhua Shi. (Negative values were set to 0 and values greater than 100% were set to 100%). Other missing values were dropped. The exposure values and covariate data may need to updated depending on study being done.  
* - rce_location
  - `~/shared_space/ci3_mdaneshyazdi/ Merged_Data/data/denominator.rds` and `~/shared_space/ci3_mdaneshyazdi/ Merged Data/denominator.fst`
* - fasse_location
  - `merged_denominator_clean_0619_exp_conf`
* - files
  -
```
```
   ├── denominator.rds
   └── denominator.fst
```
`````

`````{dropdown} 17. Hospital Admissions Merged with Denominator, Exposure, and Covariates
```{list-table}
:header-rows: 0
* - dataset_author
  - Mahdieh Danesh Yazdi
* - date_created
  - Jun 2021
* - data_source
  - MedPar (admissions), MBSF (denominator)
* - spatial_coverage
  - US
* - spatial_resolution
  - zipcode
* - temporal_coverage
  - 2000-2016
* - temporal_resolution
  - annually
* - processing_description
  - The clean denominator file merged with the clean hospital admissions data, limited to FFS patients, and then merged with annual PM2.5, NO2, O3 levels and Warm-season O3 levels from 1-km exposure models generated by Qian Di and Weeberb Requia aggregatetd to zip code level by Yaguang Wei. Also merged with covariate data from the Census, ACS, BRFSS, and Dartmouth Health Atlas created by Ben Sabath. Missing values were filled in using interpolated/extrapolated values from Liuhua Shi. (Negative values were set to 0 and values greater than 100% were set to 100%). Other missing values were dropped. The exposure values and covariate data may need to updated depending on study being done. Individuals may have multiple admissions per year. 
* - size
  - 32 GB
* - rce_location
  - `~/shared_space/ci3_mdaneshyazdi/ Merged_Data/data/national_exp_0621.fst`
* - fasse_location
  - `national_exp_0621`
* - files
  -
```
```
   └── national_exp_0621.fst
```
`````
