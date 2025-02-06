# LEGO Data Model

#### Overview

The LEGO Data Model is a structured framework designed to standardize data storage, structure, and management across various projects. By adopting a modular approach—similar to LEGO building blocks—we ensure consistency, reproducibility, and scalability in data organization.

[🔗 Access the LEGO Catalog](https://lego-catalog.netlify.app/#/dataset/lego/v0)

#### Why the LEGO Data Model?

The LEGO Data Model is inspired by the modularity and standardization of LEGO blocks. Its key principles include:
- Modular Structure: Data is organized into well-defined, reusable components.
- Standardized Formats: Ensures interoperability between datasets.
- Hierarchical Organization: Data is structured by domains, subdomains, and time resolutions.
- Predefined Schema: Every dataset follows a standard schema with linking elements like county IDs.

#### Data Standards in the LEGO Data Model

##### File Formats
To optimize storage and processing, the LEGO Data Model supports:
- Parquet: Columnar storage format for tabular data. 
- Shapefile (SHP): Used for spatial data. 

##### Folder Structure & Naming Conventions
All datasets in our lab follow a structured hierarchy to ensure logical arrangement and easy access.

##### Folder Hierarchy Example
```
<main lab folder>/lego
├── <domain>
│   ├── <subdomain>__<data_source>
│   │   ├── <geo_resolution>__<time_resolution>
│   │   │   ├── <filename>_yyyy.parquet
```

##### Key Folder Components

- Domain: Broad research category (e.g., health, environment, social).
- Subdomain: Specific dataset type (e.g., hospitalization, demographics, air pollution).
- Data Source: The origin of the dataset (e.g., Medicare, Medicaid).
- Geographic Resolution: The spatial granularity (e.g., county, state, ZCTA).
- Time Resolution: The temporal frequency (e.g., annual, monthly, daily).
- File Naming Convention: Maintains consistency for dataset identification.

##### Notes
- Files are stored yearly.
- All files that share a common datapath/filename should have identical variables/columns.

#### Navigating the LEGO Data Model Website

The LEGO Data Model includes five subdatasets, accessible via : /n/dominici_nsaph_l3/Lab/lego (FASSE path) and /n/dominici_lab/lab/lego (Cannon path)

##### Contents and Sub-datasets

The Contents and Sub-datasets tabs list available datasets:

- Medicare – Core datasets related to Medicare beneficiaries, encompassing health outcomes such as mortality, hospital admissions, and conditions including cardiovascular diseases, respiratory diseases, cancer, asthma, Alzheimer's disease and related dementias, among others.
- Legacy Medicare – Old Medicare beneficiary summary files with pre-selected variables. These datasets provide insights into health outcomes such as mortality, hospital admissions, and conditions including cardiovascular diseases, respiratory diseases, cancer, asthma, - Alzheimer's disease and related dementias.
- Environmental – Datasets capturing environmental exposures, including climate-related factors (temperature, cyclones, humidity, heat alerts, and heat waves) and pollution data.
- Geoboundaries – Geographical datasets containing shapefiles, crosswalks, and unique geospatial identifiers sourced from the U.S. Census Bureau.
- Social – Datasets derived from the U.S. Census Bureau, providing demographic and socioeconomic insights such as population distribution by age groups, ethnic composition, housing statistics, and other key social variables.

##### Dataset Details

Each dataset page provides:
- Description – Overview of dataset descriptions, folder path, and contents.
- Keywords – Tags for quick identification (e.g., health, pollution).
- Properties – Details on dataset subdivisions (e.g., mortality, geographies).

#### Example: Navigating the Medicare Core Datasets

 - Access the Dataset Overview : Navigate to the Contents tab and select Medicare Dataset. View the dataset description, metadata, file path, and keywords.
 - View Subdatasets : Click the Subdatasets tab to explore related files (e.g., mortality, admissions, outcomes).
 - Explore Specific Files : Select a subdataset → Open file path & contents (e.g., `zcta_yearly → counts_yyyy.parquet`). Click on a file to view data dictionary.

#### Leveraging the LEGO Data Model for Data Requests

The LEGO Data Model centralizes data discovery, ensuring consistency, collaboration, and reproducibility. Researchers can search metadata using the contents, datapaths, data dictionary tabs, view the pipeline on github, and collaborate seamlessly with shared dataset structures. 
