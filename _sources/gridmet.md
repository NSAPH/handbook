# Gridmet

## Quick Reference
* - dataset_name
  - GRIDMET
* - dataset_author
  - Nate Fairbank
* - date_created
  - 15JUL22
* - data_source
  - GRIDMET, Census Bureau
* - spatial_coverage
  - Continental US
* - spatial_resolution
  - 4x4km aggregated to zipcode (really to Zip Code Tabulation Area)
* - temporal_coverage
  - 2000-2018
* - temporal_resolution
  - daily
* - processing_description
  - Stage 1: Crosswalk Development (done in ArcGIS):
      1) GRIDMET's 4x4km grid was imported and transformed into defined polygon formats (rather than raster or point features)
      2) Census Bureau's ZCTA shapefiles for that year were imported
      3) The "tabulate intersection" tool was used to calculate, for each ZCTA/grid pair, the proportion of the ZCTA's area that the grid square contributed. For example, if ZCTA 12345 overlapped 3 grids, there would be three rows: (12345, Grid A, .4), (12345, Grid B, .2), (12345, Grid C, .4). 
      4) The crosswalk produced in step 3 was exported
  - Stage 2: Area-weighted aggregation:
      1) The crosswalk for that year is is imported. 
      2) For each day, the GRIDMET file is imported. 
      3) The data for each grid (all 16 variables) is joined to the crosswalk by lat/long pair for that grid. Note that if a grid square overlaps, say, three ZCTAs, then its data will be repeated 3 times so that it can be weighted appropriately for each ZCTA.
      4) The data is multiplied by the ZCTA proportion for that grid square. 
      5) The data is grouped by ZCTA with the aggregation method "sum". 
      6) That day is appended to the netCDF file
      7) An annual netCDF file is exported. 
      

* - fasse_location
  - /n/dominici_nsaph_l3/data/gridmet/

## About this project
This project is the first component of a broader effort to create reproducable tools that can re-aggregate exposure data into social boundaries such as zip codes or census tracts that can be then joined with data available at those social units such as Medicare or Census data. 

Specifically it does the following: 

1) Start point: GRIDMET climate data (4x4km grid), Census Bureau Zip Code Tabulation Area (ZCTA) boundaries
2) Aggregation technique: area weight
3) Output: ZCTAs with the area-weighted average of each GRIDMET variable

## Data sources

- GRIDMET data: https://www.northwestknowledge.net/metdata/data/permanent/
- Census Bureau Zip Code Tabulation Area (ZCTA) TIGER/Line Files and Shapefiles: https://www.census.gov/geographies/mapping-files/time-series/geo/tiger-line-file.2000.html
     - For more about ZCTAs, read here: https://www.census.gov/programs-surveys/geography/guidance/geo-areas/zctas.html
     - ZCTAs were used because they represent the government's "best guess" at what the spacial boundaries of a zip code are. While zip codes are commonly percieved as denoting spatial boundaries, they are in fact just a collection of addresses. Furthermore, they are "working units" that are defined and changed based on the needs (and whims) of the postal service. There is a degree of compromise/subjectivity here. The best answer would be "don't use zip codes as a unit of analysis". If they must be used, ZCTAs represent the best solution. 
     - NOT ALL ZIP CODES HAVE A CORRESPONDING ZCTA. ZCTAs are a trademark of the Census Bureau, an organization fundamentally concerned with PEOPLE. Zip Codes are a trademark of the US Postal Service, an organization fundamentally concerned with MAIL. Some zip codes map to a single address or very small collection of addresses. These represent high-volume mail facilities (think like PO boxes, etc), and are NOT included as seperate ZCTAs. While frustrating from a pure data perspective (why is there all this unmatched data!?) this makes sense from a practical perspective. If a Medicare patient gave a PO Box as their address, and we use that PO Box's zip code to infer what their exposure was we'd be making an inappropriate inference, as that patient doesn't actually live inside their PO Box. If matching all these "point" zip codes is necessary, a zip to ZCTA crosswalk is available here: ~/shared_space/ci3_exposure/locations/zcta/crosswalk/
     - Because zip codes change constantly, ZCTAs have to be updated. They were first created following the 2000 census, and started receiving annual updates in 2007. Thus, this process uses the annual file for all data for that year, and the 2000 census file for years 2000-2006.
     - The Census has made major updates to the ZCTAs every decade. For the 2000 Census, they include suffixes such as "XX" and "HH" to indicate large, unpopulated land areas such as national parks and bodies of water. 
"HH" suffix used to represent large water bodies

## Processing

- What variables are in there?: All original GRIDMET varaibles are preserved. There are a total of 18: 
     - For documentation on GRIDMET variables please refer to their materials: https://www.climatologylab.org/gridmet.html
     - Primary Climate Variables (9): Maximum temperature, minimum temperature, precipitation accumulation, downward surface shortwave radiation, wind-velocity, wind direction, humidity (maximum and minimum relative humidity and specific humidity)
     - Derived variables (7): Reference evapotranspiration (ASCE Penman-Montieth), Energy Release Component*, Burning Index*, 100-hour and 1000-hour dead fuel moisture, mean vapor pressure deficit, 10-day Palmer Drought Severity Index *fuel model G (conifer forest)
     - Variables from data processing (2):
          -CRS: originally "coordinate reference system", this had a value of "1" for every grid in GRIDMET. As these grids were tabulated into ZCTAs, these "1"s were tabulated as well. Thus, this number indicates how many grids (partial or whole) were part of the area aggregation for that zip code. 
          -AreaProp: To do the area weighting, each ZCTA/grid pairing was given a percentage of how much of the ZCTA's area was contained in that grid. For each ZCTA, these proportions sum to 1, meaning that 100% of the ZCTA's area was accounted for. Thus this represents a "check" on the process. A small minority of the data does NOT sum to "1". These are cases on the edge of the map, such as the Florida Keys, that GRIDMET's data does not fully cover. 

## Notes
- Notes from the GRIDMET files (these were buried in the files themselves and might otherwise not be visible):
      -author : John Abatzoglou - University of Idaho, jabatzoglou@uidaho.edu
      -note1 : The projection information for this file is: GCS WGS 1984.
      note2 :Citation: Abatzoglou, J.T., 2013, Development of gridded surface meteorological data for ecological applications and modeling, International Journal of Climatology, DOI: 10.1002/joc.3413
      -note3 : Days correspond approximately to calendar days ending at midnight, Mountain Standard Time (7 UTC the next calendar day)

