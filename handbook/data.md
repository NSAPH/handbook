# Data sources

On this page you can find a description of common data sources and their location on the cluster.

## Health data

The following contains the description of the original/raw CMS data.

`````{dropdown} MBSF and MedPar

```{list-table}
:header-rows: 0

* - data_source
  - [MBSF](https://resdac.org/cms-data/files/mbsf-base) and [MedPar](https://resdac.org/cms-data/files/medpar)
* - description
  - MedPar includes hospitalizations for FFS individuals (1999-2018). MBSF or the enrollment file and also has mortality for everyone (1999-2018).
* - fasse_location
  - Append `/n/dominici_nsaph_l3/Lab/data/` to the beginning of the paths: `ci3_d_medicare/original_data/cms_medicare/data`
* - size
  - 733 GB
* - files
  - 
```
````{dropdown} Medicare data folder tree
```
├── 1999
│     ├── denominator
│     └── inpatient
├── 2000
│     ├── denominator
│     └── inpatient
├── 2001
│     ├── denominator
│     └── inpatient
├── 2002
│     ├── denominator
│     └── inpatient
├── 2003
│     ├── denominator
│     └── inpatient
├── 2004
│     ├── denominator
│     └── inpatient
├── 2005
│     ├── denominator
│     └── inpatient
├── 2006
│     ├── denominator
│     └── inpatient
├── 2007
│     ├── denominator
│     └── inpatient
├── 2008
│     ├── denominator
│     └── inpatient
├── 2009
│     ├── denominator
│     └── inpatient
├── 2010
│     ├── denominator
│     └── inpatient
├── 4334
│     ├── 2011
│     ├── 2012
│     ├── 2015
│     └── Extract File Documentation
├── 4580
│     ├── 2013
├── 5819
│     ├── 2014
│     └── Extract File Documentation
├── 7087
│     ├── 2015
│     └── Extract File Documentation
├── 8183
│     ├── 2016
│     └── Extract File Documentation
├── 10411
│     └── 2017
├── 2018
│     └── extract_file_documentation
├── Medicare Claims
├── Medicare Enrollment
└── Xwalk
```
````
`````

`````{dropdown} MCBS

```{list-table}
:header-rows: 0

* - data_source
  - [MCBS](https://www.cms.gov/Research-Statistics-Data-and-Systems/Research/MCBS)
* - description
  - Survey for sample of all Medicare or just FFS (1999-2004, 2007-2013, 2015-2017). Check out NSAPH MCBS documentation [here](./mcbs.md).
* - fasse_location
  - `/n/dominici_nsaph_l3/data/mcbs/`
* - size
  - placeholder
```
`````

``` {seealso}
Check out the following resources about the CMS health data:
- [RESDAC Using Medicare Hospitalization Information and the MedPAR](http://resdac.umn.edu/sites/resdac.umn.edu/files/Using%20Medicare%20Hospitalization%20Information%20and%20the%20MedPAR%20(Slides).pdf) 
- [Coverage Denials: Government And Private Insurer Policies For Medical Necessity In Medicare](https://www.healthaffairs.org/doi/pdf/10.1377/hlthaff.2021.01054)
- [RESDAC Online learning](https://resdac.org/online-learning)
- [RESDAC Learning and workshops](https://resdac.org/learn)
```

## Exposure data

The following is the description of the air pollution exposure data.

### ZIP code-level PM2.5, PM2.5 components, Ozone, and NO2 in the contiguous US

`````{dropdown} PM2.5, Ozone, NO2
```{list-table}
:header-rows: 0
* - dataset_author
  - Yaguang Wei
* - date_created
  - Oct 19, 2022
* - data_source
  - Gridded PM2.5, PM2.5 components, ozone, and NO2; Esri ZIP code area and point files; U.S. ZIP code database.
* - spatial_coverage
  - US
* - spatial_resolution
  - zipcode
* - temporal_coverage
  - 2000-2016 for PM2.5, ozone, and NO2; 2000-2019 for PM2.5 components.
* - temporal_resolution
  - daily, annually
* - description
  - For general ZIP Codes with a polygon representation, we estimated their pollution levels by averaging the predictions of grid cells whose centroids lie inside the polygon of that ZIP Code; For other ZIP Codes such as Post Offices or large volume single customers, we treated them as a single point and predicted their pollution levels by assigning the predictions of the nearest grid cell. These are updated ZIP code-level predictions. We filled in the missing values for grids, and added about 200 zip codes that are missing in the Esri files each year. The geographic information for the additional zip codes is extracted from US ZIP code database. **Version 2 update:** The v2 files (`exposure/ozone/O3_v2`, `exposure/pm25/PM25_v2`, `exposure/no2/NO2_v2`): (1) exclude zip codes that are outside the contiguous US; (2) a `state` column is added to each file, so we know which zip code belongs to which state. No exposure values were changed. This version (v2) is available on [NASA SEDAC]((https://sedac.ciesin.columbia.edu/data/set/aqdh-pm2-5-o3-no2-concentrations-zipcode-contiguous-us-2000-2016)).
* - git_repository
  - [ZIP_add_missing](https://github.com/NSAPH-Data-Processing/ZIP_add_missing) and private [ZIP_add_missing](https://github.com/yycome/ZIP_add_missing)
* - publication
  - The data are officially published through NASA SEDAC at [sedac.ciesin.columbia.edu](https://sedac.ciesin.columbia.edu/data/set/aqdh-pm2-5-o3-no2-concentrations-zipcode-contiguous-us-2000-2016).
* - fasse_location
  - Add `/n/dominici_nsaph_l3/Lab/data/` to the beginning of the paths: `exposure/ozone/O3_v1`, `exposure/ozone/O3_v2`, `exposure/pm25/PM25_v1`, `exposure/pm25/PM25_v2`, `exposure/no2/NO2_v1`, `exposure/no2/NO2_v2`, `exposure/pm25_components/pm25_components_v2`
* - files
  -
```
```
├── [2.3G]  NO2
│   ├── [6.5M]  Annual
│   │   ├── [394K]  2000.rds
│   │   ├── [391K]  ...
│   │   └── [391K]  2016.rds
│   └── [2.3G]  Daily
│       ├── [393K]  20000101.rds
│       ├── [392K]  ...
│       └── [395K]  20161231.rds
├── [2.3G]  O3
│   ├── [6.4M]  Annual
│   │   ├── [390K]  2000.rds
│   │   ├── [385K]  ...
│   │   └── [384K]  2016.rds
│   ├── [2.3G]  Daily
│   │   ├── [394K]  20000101.rds
│   │   ├── [388K]  ...
│   │   └── [371K]  20161231.rds
│   └── [6.5M]  Summer
│       ├── [391K]  2000_summer.rds
│       ├── [387K]  ...
│       ├── [386K]  2016_summer.rds
│       └── [ 101]  readme.txt
├── [2.3G]  PM25
│   ├── [6.5M]  Annual
│   │   ├── [395K]  2000.rds
│   │   ├── [392K]  ...
│   │   └── [392K]  2016.rds
│   └── [2.3G]  Daily
│       ├── [397K]  20000101.rds
│       ├── [395K]  ...
│       └── [393K]  20161231.rds
├── [ 88M]  PM25_components
│   ├── [4.4M]  2000.rds
│   ├── [4.4M]  ...
│   ├── [4.4M]  2019.rds
│   └── [ 850]  readme.txt
└── [ 974]  README.md
```
`````

### PM2.5 Components - Obsolete

`````{dropdown} PM2.5 component data
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
  - Superseded by `/n/dominici_nsaph_l3/Lab/data/exposure/ pm25_components/pm25_components_v2`. These are annual estimations of PM2.5 speciations at ZIP Code-level  across the contiguous US, aggregated from Heresh's grid-level estimations. For a general ZIP Code, which has normal street delivery route and therefore can be represented by a polygonal area, we estimate the ZIP Code-level PM2.5 by averaging the predictions of grid cells whose centroids lie inside the polygon of that ZIP Code; for other ZIP Codes that do not have polygon representations, for example an apartment building, a military base, or a post office, we consider them as single points and estimate their ZIP Code-level PM2.5 by linking the prediction of the nearest grid cell. For ec, oc, nh4, no3, and so4 the units are microgram per cubic meter; for br, ca, cu, fe, k, ni, pb, si, v, and z the units are nanogram per cubic meter.
* - fasse_location
  - Append `/n/dominici_nsaph_l3/Lab/data/` to the beginning of the paths: `exposure/pm25_components/pm25_components_v1`
* - git_repository
  - https://github.com/yycome/PM25_Components
* - publication 
  - Amini, H., M. Danesh-Yazdi, Q. Di, W. Requia, Y. Wei, Y. Abu Awad, L. Shi, M. Franklin, C.-M. Kang, J. M. Wolfson, P. James, R. Habre, Q. Zhu, J. S. Apte, Z. J. Andersen, X. Xing, C. Hultquist, I. Kloog, F. Dominici, P. Koutrakis, J. Schwartz. 2022. Annual Mean PM2.5Components (EC, NH4, NO3, OC, SO4) 50m Urban and 1km Non-Urban Area Grids for Contiguous U.S., 2000-2019 v1. (Preliminary Release). Palisades, NY: NASA Socioeconomic Data and Applications Center (SEDAC). https://doi.org/10.7927/7wj3-en73
* - dataset_author
  - Yaguang Wei
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

### Predicted daily smoke PM2.5 over the Contiguous US, 2006 - 2020

`````{dropdown} Predicted daily smoke PM2.5
```{list-table}
:header-rows: 0
* - dataset_author
  - Marissa Childs
* - date_created
  - October 24, 2020
* - data_source
  - other (exposure predictions)
* - spatial_coverage
  - Contiguous US
* - spatial_resolution
  - originally 10 km (gridded), aggregated to zcta, census tract, and county by area and population-weighted averages
* - temporal_coverage
  - 2006 - 2020
* - temporal_resolution
  - daily
* - exposures
  - PM2.5 from smoke 
* - processing_description
  - none
* - fasse_location
  - Append `/n/dominici_nsaph_l3/Lab/data/` to the beginning of the paths: `exposure/predicted_daily_smoke_pm25`
* - publication
  - https://doi.org/10.1021/acs.est.2c02934 
* - git_repository
  - [daily-10km-smokePM](https://github.com/echolab-stanford/daily-10km-smokePM)
* - size
  - 6 GB
* - files
  -
```
```
├── 10km_grid
│   ├── 10km_grid_wgs84
├── county
│   └── tl_2019_us_county
├── tract
│   └── tracts
│       ├── tl_2019_01_tract
│       ├── tl_2019_04_tract
│       ├── ... 
│       └── tl_2019_56_tract
└── zcta
    └── tl_2019_us_zcta510
```
`````

## Confounder data

### Gridmet

This project aggregates Gridmet data into social boundaries such as zip codes or census tracts 
that can be then joined with data available at those social units such as Medicare or Census data. Specifically it does the following: 

1. Start point: GRIDMET climate data (4x4km grid), Census Bureau Zip Code Tabulation Area (ZCTA) boundaries
2. Aggregation technique: area weight
3. Output: ZCTAs with the area-weighted average of each GRIDMET variable

`````{dropdown} Gridmet data

```{list-table}
:header-rows: 0
* - fasse_location
  - `/n/dominici_nsaph_l3/Lab/data/data/gridmet/`
* - dataset_author
  - Nate Fairbank
* - date_created
  - July 15, 2022
* - spatial_coverage
  - Continental US
* - spatial_resolution
  - 4x4km aggregated to Zip Code Tabulation Area (ZCTA)
* - temporal_coverage
  - 2000-2018
* - temporal_resolution
  - daily
* - data_source
  - GRIDMET, Census Bureau
```
``` {dropdown} data_source description
1. [GRIDMET data](https://www.northwestknowledge.net/metdata/data/permanent/)

All original GRIDMET varaibles are preserved. There are a total of 18: 
  - Primary Climate Variables (9): Maximum temperature, minimum temperature, precipitation accumulation, downward surface shortwave radiation, wind-velocity, wind direction, humidity (maximum and minimum relative humidity and specific humidity)
  - Derived variables (7): Reference evapotranspiration (ASCE Penman-Montieth), Energy Release Component*, Burning Index*, 100-hour and 1000-hour dead fuel moisture, mean vapor pressure deficit, 10-day Palmer Drought Severity Index *fuel model G (conifer forest)
  - Variables from data processing (2):
       - CRS: originally "coordinate reference system", this had a value of "1" for every grid in GRIDMET. As these grids were tabulated into ZCTAs, these "1"s were tabulated as well. Thus, this number indicates how many grids (partial or whole) were part of the area aggregation for that zip code. 
       - AreaProp: To do the area weighting, each ZCTA/grid pairing was given a percentage of how much of the ZCTA's area was contained in that grid. For each ZCTA, these proportions sum to 1, meaning that 100% of the ZCTA's area was accounted for. Thus this represents a "check" on the process. A small minority of the data does NOT sum to "1". These are cases on the edge of the map, such as the Florida Keys, that GRIDMET's data does not fully cover. 
- For documentation on GRIDMET variables please refer to [their materials](https://www.climatologylab.org/gridmet.html).
- Notes from the GRIDMET files:
    - author: John Abatzoglou - University of Idaho, jabatzoglou@uidaho.edu
    - The projection information for this file is: GCS WGS 1984.
    - Citation: Abatzoglou, J.T., 2013, Development of gridded surface meteorological data for ecological applications and modeling, International Journal of Climatology, DOI: 10.1002/joc.3413
    - Days correspond approximately to calendar days ending at midnight, Mountain Standard Time (7 UTC the next calendar day)
    
2. [Census Bureau Zip Code Tabulation Area (ZCTA) TIGER/Line Files and Shapefiles](https://www.census.gov/geographies/mapping-files/time-series/geo/tiger-line-file.2000.html)

ZCTAs were used because they represent the government's "best guess" at what the spacial boundaries of a zip code are. While zip codes are commonly percieved as denoting spatial boundaries, they are in fact just a collection of addresses. Furthermore, they are "working units" that are defined and changed based on the needs (and whims) of the postal service. There is a degree of compromise/subjectivity here. The best answer would be "don't use zip codes as a unit of analysis". If they must be used, ZCTAs represent the best solution. 
- NOT ALL ZIP CODES HAVE A CORRESPONDING ZCTA. ZCTAs are a trademark of the Census Bureau, an organization fundamentally concerned with PEOPLE. Zip Codes are a trademark of the US Postal Service, an organization fundamentally concerned with MAIL. Some zip codes map to a single address or very small collection of addresses. These represent high-volume mail facilities (think like PO boxes, etc), and are NOT included as seperate ZCTAs. While frustrating from a pure data perspective (why is there all this unmatched data!?) this makes sense from a practical perspective. If a Medicare patient gave a PO Box as their address, and we use that PO Box's zip code to infer what their exposure was we'd be making an inappropriate inference, as that patient doesn't actually live inside their PO Box. If matching all these "point" zip codes is necessary, a zip to ZCTA crosswalk is available here: `/n/dominici_nsaph_l3/Lab/data/shapefiles/`
- Because zip codes change constantly, ZCTAs have to be updated. They were first created following the 2000 census, and started receiving annual updates in 2007. Thus, this process uses the annual file for all data for that year, and the 2000 census file for years 2000-2006.
- The Census has made major updates to the ZCTAs every decade. For the 2000 Census, they include suffixes such as "XX" and "HH" to indicate large, unpopulated land areas such as national parks and bodies of water. 
- "HH" suffix used to represent large water bodies
- For more about ZCTAs, read [here](https://www.census.gov/programs-surveys/geography/guidance/geo-areas/zctas.html)
```
``` {dropdown} processing_description
- Stage 1: Crosswalk Development (done in ArcGIS):
    1. GRIDMET's 4x4km grid was imported and transformed into defined polygon formats (rather than raster or point features)
    2. Census Bureau's ZCTA shapefiles for that year were imported
    3. The "tabulate intersection" tool was used to calculate, for each ZCTA/grid pair, the proportion of the ZCTA's area that the grid square contributed. For example, if ZCTA 12345 overlapped 3 grids, there would be three rows: (12345, Grid A, .4), (12345, Grid B, .2), (12345, Grid C, .4). 
    4. The crosswalk produced in step 3 was exported
- Stage 2: Area-weighted aggregation:
    1. The crosswalk for that year is is imported. 
    2. For each day, the GRIDMET file is imported. 
    3. The data for each grid (all 16 variables) is joined to the crosswalk by lat/long pair for that grid. Note that if a grid square overlaps, say, three ZCTAs, then its data will be repeated 3 times so that it can be weighted appropriately for each ZCTA.
    4. The data is multiplied by the ZCTA proportion for that grid square. 
    5. The data is grouped by ZCTA with the aggregation method "sum". 
    6. That day is appended to the netCDF file
    7. An annual netCDF file is exported. 
```
`````

## Shapefiles

`````{dropdown} zcta_shape_files

```{list-table}
:header-rows: 0
* - fasse_location
  - `/n/dominici_nsaph_l3/Lab/data/shapefiles`
* - files
  -
```
```
└── zcta_shape_files
     ├── cb_2018_us_zcta510_500k.cpg
     ├── cb_2018_us_zcta510_500k.dbf
     ├── cb_2018_us_zcta510_500k.prj
     ├── cb_2018_us_zcta510_500k.shp
     ├── cb_2018_us_zcta510_500k.shp.ea.iso.xml
     ├── cb_2018_us_zcta510_500k.shp.iso.xml
     └── cb_2018_us_zcta510_500k.shx
```
`````

`````{dropdown} zip_shape_files

```{list-table}
:header-rows: 0
* - fasse_location
  - `/n/dominici_nsaph_l3/Lab/data/shapefiles`
* - files
  -
```
```
└── zip_shape_files
    ├── 2000
    ├── 2004
    ├── 2005
    ├── 2006
    ├── 2007
    ├── 2009
    ├── 2010
    ├── 2012
    ├── 2013
    ├── 2014
    ├── 2015
    ├── 2016
    └── 2017
```
`````

### ZIP to ZCTA crosswalk (2015)
`````{dropdown} **zip_to_zcta**
```{list-table}
:header-rows: 0
* - rce_location
  - `~/shared_space/ci3_exposure/locations/zcta/crosswalk/`
* - fasse_location
  - `/n/dominici_nsaph_l3/Lab/data/shapefiles/zip_to_zcta`
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

## Other data 

The following are other commonly-used public data sources, many of which may be found in the **confounders** folder on FASSE.

- [CMS Synthetic data: 2008, 2009, and 2010](https://www.cms.gov/Research-Statistics-Data-and-Systems/Downloadable-Public-Use-Files/SynPUFs/DE_Syn_PUF)
- [CDC, Behavioral Risk Factor Surveillance System (BRFSS) data for body mass index and smoking status](https://www.cdc.gov/brfss/annual_data/annual_2008.htm)
- [PM2.5 concentrations (US) from Di et al. 2019](https://beta.sedac.ciesin.columbia.edu/data/set/aqdh-pm2-5-concentrations-contiguous-us-1-km-2000-2016)
- [Census data](https://www.census.gov/data/developers/data-sets/acs-5year.2010.html)
- [GridMET data](https://www.climatologylab.org/gridmet.html)
- [County Presidential Election Returns 2000-2020](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/VOQCHQ&version=10.0)
- [United States Broadband Usage Percentages Dataset](https://github.com/microsoft/USBroadbandUsagePercentages)

